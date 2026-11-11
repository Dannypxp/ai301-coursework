# Contribution: [Issue Title]

Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** Daniel Vivar
**GitHub Username:** Dannypxp
**Issue:** https://github.com/hololinked-dev/hololinked/issues/207
**Pull Request:** [GitHub PR link, once opened]

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: [one line on the tool work]**

[2-4 sentences: what you built (the scout, your strategy), what broke
or fell short, what changed because of it.]

Built the Issue Scout to search for an issue on github that matches my rubric which explains what type of work I am interested and comfortable with. This work includes the language python and focusing on security aspects of projects to align with my cybersecurity career. Originally my rubric was missing a couple key checks which did not allow my tool to work the first time, adding the Issue Open check made sure to properly only approve issues that were not closed or taken by another coder. 

**Unit 6: [one line on the tool work]**

[2-4 sentences: the voice-guard, the repo-memory file. What broke or
fell short, and what changed because of it. "Nothing broke" counts when
it is true - say how you know.]

The Voice guard and repo-memory file both worked well, while submitting the claim comment it was
 stopped by the voice gaurd for containing the specific versions of the packages and the operating system.
 The repo-memory file helps alot aswell because it helps claude remember the repo everytime it is re-opened and 
 stays in the bounds of the repos rules.

**Unit 7: [one line on the tool work]**

[2-4 sentences: the ship-gate and your gate manifest. What it produced
on your real branch, what fought you, what changed because of it.]

**Unit 8: [one line on the tool work]**

[2-4 sentences: the PR-monitor and your playbook. What it read, what it
drafted, what you did with the draft.]

---

## Why I Chose This Issue

[1-2 paragraphs in your own words: how you searched, what your scan
surfaced, what your scout's verdict said, why this issue fits your
profile, and what you hope to learn. If your scout's verdict on it
was reject and you chose it anyway, say so here and say why; choosing
against your own tool silently is what loses points. Close with an
honest read of the tool itself: where the scout fell short on a real
wild search and what you changed or would change, or what convinced
you it held up. **Record the link to your claim comment in this section too.**
Not claimed yet? Write `claim pending` and today's date where the link goes,
and add the link the moment your claim lands.]

When searching for my issue, Using the class provided repo search tool I first looked for security related 
repos to match my background in cybersecurity. Running the scan on the issue produced an accept for the issue 
because the scope is for a first contribution and doesnt include languages i specified against. 
The issue scout held up great for the issue because it made sure it was still open and was apart of an active 
repo by checking when the maintainer last replied or interacted with pull requests.

https://github.com/hololinked-dev/hololinked/issues/207#issuecomment-6564112110
**Toolkit**

- Tool: issue-scout (your scout: The search strategy was to find active repo's with specific activity from the maintainers and activity with merging repos, 
Check	Evidence	Pass condition	Weight
Repo Merge	last push to any branch	last merge under 2 months old	required
Maintainer Reply	maintainer first-response sample	last reply by a maintainer under 2 weeks	preferred
Other Active Issues	open issues + PRs	other issues are active	required
Issue Open	the issue	issue is currently open	required
scope-feasible	issue body: the work it asks for	one identifiable piece of work someone could start; fails only for a codebase-wide checklist, an "improve X everywhere", or a container issue tracking many sub-tasks	required
)
- What it produced: The scan produced an accept verdict and made sure it was an active repo to commit to. It checked 
how recent the a repo was merged, if the maintainer replies to any issue and if any other issues are currently active.
- Difficulties: "none met"
- What changed: "nothing

---

## Understanding the Issue

**Problem Description**

[In your own words, what is broken or missing?]

Adding fields to a ZMQ Message header which incluve authorization, version and timestamp. Aswell, updating the zmq messaging docoumentation to explain the new fields

**Expected Behavior**

Messages now sent using the ZMQ format should include the timestamp of the server and object communication, authorization field for future iplementation of api keys and a version field which rejects any connection without the matching version and raises and error before timeout

**Current Behavior**

Messages sent using the ZMQ Format hold various different fields in the header like 
messageType, messageID, senderID, receiverID, serverExecutionContext, thingExecutionContext, thingID, objekt, operation, payloudContentType, preencodedPayloadContentType

**Affected Components**

Ther part of the codebase that is involvled is the zmq messaging which includes the files server/zmq/message.py, server/zmq/request_message_header_schema.josn, server/zmq/response_message_header_schema.josn

**Toolkit**

- Tool: Ship-gate
- What it produced: It produces a valid PR when all checks that I have iplemented into the ship-gate from the contributing.md of the repo.
- Difficulties: N/A
- What changed: Adding both scripts for the tests and ruff check that has to occur before submitting a pr

---

## Reproduction Process

**Environment Setup**

[What a stranger would need to stand this up: your operating system,
the relevant versions (language, runtime, package manager, the project
itself), and how you set the project up. Then the challenges you faced
and how you solved them, or that none came up.]

Operating System: MacOs 27.2
Python: 3.11.15

1. Clone hololinked-main v0.4.2
2. Open Folder in VSCode
3. In root directory, 
run - 
uv venv (if venv is not installed (brew install uv))
source .venv/bin/activate
uv sync
4. Installation is succesful


**Steps to Reproduce**

1. Create python test file "test_header_variables.py"
2. paste script to test the header fields

import msgspec
from hololinked.server.zmq.message import RequestHeader, ResponseHeader

for cls in (RequestHeader, ResponseHeader):
    for f in msgspec.structs.fields(cls):
        print(cls.__name__, f.name, f.type, f.required, f.default)

3. Run script with 'python3 test_header_variables.py'

4. Result

RequestHeader messageType <class 'str'> True NODEFAULT
RequestHeader messageID <class 'str'> True NODEFAULT
RequestHeader senderID <class 'str'> True NODEFAULT
RequestHeader receiverID <class 'str'> True NODEFAULT
RequestHeader serverExecutionContext <class 'hololinked.core.eventloop.operations.SchedulerExecutionContext'> False NODEFAULT
RequestHeader thingExecutionContext <class 'hololinked.core.eventloop.operations.ThingExecutionContext'> False NODEFAULT
RequestHeader thingID str | None False 
RequestHeader objekt str | None False 
RequestHeader operation str | None False 
RequestHeader payloadContentType str | None False application/json
RequestHeader preencodedPayloadContentType str | None False text/plain
ResponseHeader messageType <class 'str'> True NODEFAULT
ResponseHeader messageID <class 'str'> True NODEFAULT
ResponseHeader receiverID <class 'str'> True NODEFAULT
ResponseHeader senderID <class 'str'> True NODEFAULT
ResponseHeader payloadContentType str | None False application/json
ResponseHeader preencodedPayloadContentType str | None False 

This script proves the timestamp, authorization and version fields do not exist

**Reproduction Evidence**

- **Commit showing reproduction:** none
- **Screenshots/logs:** [if applicable]
- **My findings:** [what you discovered during reproduction; an
  honest, evidenced cannot-reproduce that led you to re-pick or ask
  the maintainer belongs here and costs you nothing]

**Toolkit**

- Tool: repro-check
- What it produced: It produced a verdict whether my repro draft accuratly followed the statements made in my claim comment and wether the issue was properly reproduced/tested
- Difficulties: No difficulties was present while running the claude skill, it provided helpful information about the files I will be working on and if my claims were true about my findings during testing.
- What changed: The toolkit was not changed while scanning my repro draft.

---

## Solution Approach

**Analysis**

hololinked/server/zmq/message.py shows both RequestHeader and ResponseHeader classes are missing the timestamp, version and authorization fields. To implement my changes I will have to update the file hololinked/server/zmq/message.py which includes both the request and response header for zmq messages. I will need to add the new fields as strings and an int, which include the timestamp, authorization and version fields.

**Proposed Solution**

I'm going to add the new fields in the message.py file in the RequestHeader and ResponseHeader class which also already includes various different fields. Furthermore, update the hololinked-main/hololinked/server/zmq/request_message_header_schema.json and hololinked-main/hololinked/server/zmq/response_message_header_schema.json with the new fields and written explanations. Furthermore, to enforce the version check at the handshake level I will need to add the version check in brokers.py in the AsyncZMQServer._handshake and SyncZMQClient.handshake class. Not changing any other file in the zmq folder.

**Implementation Plan**

1. Create a template for fields timestamp, version and authorization
2. Create authorization field as a string and empty, nothing needs to be implemented inside the header
3. Create the timestamp field with a python function which records the exact time communication between the server and client occur, with microsecond precision
4. Create the version field, enforce at handshake and raise error if version does not match for the server and client, a ConnectionRefusedError would be raised instantly on the server instead of waiting 60 seconds for a ConnectionTimeout error.
5. Update the request and response message header schema with the new fields
6. Add the version check to hololinked-main/hololinked/server/zmq/brokers.py in AsyncZMQServer._handshake and SyncZMQClient.handshake classes. I will enforce a server side ConnectionRefusedError if the versions don't match.
7. Create tests for ZMQ messaging with both the matching and mismatch contract versions. A new file zmq_message_version_test.py will test the mismatch and is expected to produce a ConnectionRefusedError and the match case is expected to produce an error-free connection.


[Record deviations here as they happen: what changed mid-build and
why. A recorded deviation is honest work; silent drift is not.]

**Toolkit**

- Tool: plan-check
- What it produced: Produced a verdict which informed me if my plan followed my previous comments on the issues page. Aswell, the checks in my plan-check skill made sure to see if I acknowledge the correct diagnosis for the issue, mention all the files I will edit, if a repro comment has an expected outcome and if AI code is allowed in the repo.
- Difficulties: The checks in plan-check are more effective for issues with clear errors and less for issues with new features/additions. 
- What changed: plan-check was not changed.

---

## Testing Strategy

[What observable checks prove the fix: your reproduction steps re-run
against the built change (before and after), and the repo's own test
suite or checks with the outcome shown. "Tests pass" with nothing
observable named is not a strategy.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Implementation Notes

[A running log, added to as you work. Date each entry. What you
built, decisions you made when you made them, wrong turns included.]

**[Date]**

[Entry]

**[Date]**

[Entry]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Pull Request

**PR Link:** [GitHub PR URL when opened]

**PR Description:** [what the PR says; much of the content above
adapts into it]

**Maintainer Feedback:**

- [Date]: [feedback received, or "none yet"; silence is a normal
  state and costs you nothing]
- [Date]: [how you addressed it]

**Status:** [Awaiting review / Iterating / Merged / Closed. The
status is a fact you record, never a grade: the PR is graded as
opened.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Learnings and Reflections

**Technical Skills Gained**

[What you learned technically, named concretely.]

**Challenges Overcome**

[What was hard and how you solved it; point at the real events, the
Toolkit blocks above are full of them.]

**What I'd Do Differently Next Time**

[Reflection on your process.]

---

## Resources Used

[What actually helped, not a reading list. List things this story
already shows you using: the doc you followed to set the environment
up, the thread that explained the bug, the person who answered you.
One real entry beats ten plausible ones.]

- [Link to documentation that helped]
- [Discussion, issue, or post that helped]
