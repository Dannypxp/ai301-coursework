# I Implemented new fields in a zmq message header for the open source project Hololinked

## Overview

For the open source project Hololinked, I submitted my first ever pull request and it was for issue 207 which required the addition of three new fields to a zmq message header. These new fields were for the request and response headers for zmq communications between a server and client which included adding the authorization, version and timestamp fields. I added these fields and generated propertests, futhermore I updated the header schema to make sure the new fields are properly understood. This issue is currently blocking a different issue which requires the authorization field to be implemented to allow the support for API key authorization for ZMQ.

Pull Request: https://github.com/hololinked-dev/hololinked/pull/217

## What Happened

I started by asking Claude to explain the core concepts behind the issue, because the codebase was new to me and I needed to understand what my pull request was being asked to do. This took the longest. I thought the issue was too hard, so my claim comment asked the maintainer whether a partial pull request would be acceptable. He agreed and encouraged me, and once I started building I found a full pull request was realistic. I used my Claude skills to draft the plan and to grade it against the issue description and my claim comment, to check it stayed in scope.

"Plan -

will add timestamp and authorization fields to header first

Will add tests for ConnectionRefusedError that will be thrown for version mismatches that is enforced on handshake

Will update request_message_header_schema.json and response_message_header_schema.json with the new message fields"

I opened PR #217 on Nov 11. The maintainer reviewed it the next day. One comment questioned a piece of code I had added to the handshake:

"I am not sure if tracking handshake IDs are useful."

Before removing it, I wanted to know what the tracking protected against. Without it, a stale error reply from an earlier request would be read during a handshake and treated as a refusal. I wrote a script that put such a reply in the client's socket first. The output showed the difference:


[current code, with handshake_ids check] handshake OK (stale ERROR ignored)
[patched, ID check removed] handshake RAISED RuntimeError: stale error from an earlier request
I then tested whether a real reconnect could hit this, using the client pool with servers that die right after sending errors. Across 32 trials the pool read the replies first and no stale error reached a handshake. So I removed the tracking as he suggested. This is a limited test, not a production rate.

The maintainer also pushed two suggestion commits to my branch on Nov 15. After I pulled them, the code failed. The first one had an indentation error at brokers.py:729, so the module would not import. His version also passed a string where an exception was expected. After I fixed the indentation, the version-mismatch tests failed because the client got a generic exception, not ConnectionRefusedError:


E   Exception: message contract version mismatch, client 'test-version-client-fad1a933' sent 'v1', server 'test-version-server-884a4beb' expects 'v2'
Before (as pulled), with the broken indentation:


             message = f"message contract version mismatch, ..."
             await self._handle_error_message(request_message, message)
            return
After:


await self._handle_error_message(
    request_message,
    ConnectionRefusedError(
        f"message contract version mismatch, client '{request_message.sender_id}' sent "
        + f"'{request_message.header.version}', server '{self.id}' expects '{CONTRACT_VERSION}'"
    ),
)
return
A second failure came next. The tests asserted that the server traceback in the error notes mentioned _handshake:


E   assert False
E    +  where False = any(<generator object test_04_handshake_with_mismatching_version_is_refused_instantly.<locals>.<genexpr> ...>)
His simplification stopped raising the exception first, so the server no longer sends a traceback. I changed my tests by removing those two assertions and kept the checks on the exception type, the message and the 3-second refusal. I also removed the two header-field tests he called "oddly specific", added a ContractVersion enum, and removed authorization from ResponseHeader and its schema.

The related test file passes (6 tests) and the pre-commit hooks pass. I merged the latest main into my branch and pushed it.

Result: the maintainer reviewed the PR and applied two of his own suggestions to my branch. The PR has not merged yet and I am waiting for his response, so nothing has landed.

## Limitations and what's next

I believe completing this issue has left me satisfied in being able to find issues to work on and submit a completed pull request. Currently I am waiting for more feedback after removing certain tests and removing Id tracking after accepting the handshake. Next time I will definelty choose and issue that is closer to subjects I currently am knowledgable in