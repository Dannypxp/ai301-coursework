# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

[Your GitHub username, exactly as it appears on your profile - no @, no
profile URL. Your comment upstream is identified by this name, and it is
the only thing that ties it to you. Several students may plan the same
house issue, so this is what keeps their comments off your score and
yours off theirs.]

Dannypxp

**Plan comment**

[Link to the comment where you posted your plan on the issue. Use the comment's own
permalink. **Then paste the text of that comment underneath the link** — the pasted text is
what this field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/58#issuecomment-6008830926

Plan for issue #58

Reproduced issue with regex in bias_detector.py with missing common phrasing which outputs (False, ''), updating the dismissive and demographic patterns in bias_detector.py with missing words from the 9 failed tests in test_bias_detector.py will fix the failing tests and return (True, "Dismissive language about educational background"). I will provide the pr when the remaining 9 tests pass in test_bias_detector.py in branch fix/58-bias-detector-common-phrases.

---

## Your branch

**Branch**

[The name of the branch you built the change on, exactly as it appears in your fork. The
naming shape is a type prefix, then the issue number, then a short description. **The issue
number in the branch name must be the number of the issue you claimed** — a name carrying
any other number does not satisfy this field.]

fix/58-bias-detector-common-phrases

**Evidence**

[Your Unit 2 reproduction steps re-run against the built change: the before, then the
after. Paste both, including the commands you ran and their output.]


 Environment - Docker 28.0.1, Macos 27.0, Python 3.11.15
    Reproduction Steps -
    cp .env.example .env
    docker compose up -d
    make setup
    python3 -c "
    from safety.bias_detector import BiasDetector
    print(BiasDetector.detect_bias('The candidate only attended a bootcamp, so this project lacks the rigor of a formal CS education'))"
    (False, '')

    Expected - (True, "Dismissive language about educational background")

    Actual - (False, '')

    cp .env.example .env
    docker compose up -d
    make setup
    python3 -c "
    from safety.bias_detector import BiasDetector
    print(BiasDetector.detect_bias('The candidate only attended a bootcamp, so this project lacks the rigor of a formal CS education'))"

    Expected - (True, 'Dismissive language about educational background')

    Actual - (True, 'Dismissive language about educational background')

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]



<!-- 
| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
|diagnosis  |## Issue  |passes if the plan says what causes the bug.  |required  |
|scope   |## Candidate plan. ## Issue   |look where the plan says what it will change; passes if it names each file it will change and says what it won’t touch.  |required  |
|test  |## Repro evidence  |passes if it provides the steps to test the issue  |required  |
|comment  |## Candidate plan comment  |Comment properply explains how the plan is related to the issue  |Required  |
(17/20)

+++
|signals  |##Thread highlights, ##Repo facts  |comment follows issue template and AI contribution are not banned  |Required  |
(18/20)

|diagnosis  |## Issue  |passes if the plan says what causes the bug.  |required  | (18/20)
->
|diagnosis  |## Issue  |passes if the plan says what causes the bug and is supported by repro evidence |required  | (18/20)
 -->

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

In pkg-03 the golden rubric decision is an accept, my rubric also agrees because the 5 checks passed with the plan is supported by repro evidence, scope is mentioned, tests are included for the fix, and the comment explains the plan in relation to the issue

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/plan-check/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

|diagnosis  |## Issue  |passes if the plan says what causes the bug and is supported by repro evidence |required  |

The diagnosis check was altered with the line "is supported by repro evidence" because it helped reject issues which their plans did not have evidence/connection to the repro they have submitted

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

|test  |## Repro evidence  |passes if it provides the steps to test the issue  |required  | 

The test check is simple but easy to trick, it will also pass any repro with any type of test. For now making sure a repro has a test is enough.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
