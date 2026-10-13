# Unit 4 — Test and Submit

Path: `beat-1-sandbox/unit-4/pull-request.md`

Record of the pull request you opened against the Path Review repo, and of the evaluation
runs that produced `eval-run.txt`. This file is graded at the path above; a copy kept
anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your pull request

**Pull request**

[Link to the pull request you opened. It must be the pull request's own page on the Path
Review repo, not your fork's branch page.]

https://github.com/Dannypxp/pathreview-ai301-fa26-s3/pull/1

**Branch**

[The name of the branch the pull request comes from, exactly as it appears in your fork.
The naming shape is a type prefix, then the issue number, then a short description. **The
issue number in the branch name must be the number of the issue the pull request fixes** —
a name carrying any other number does not satisfy this field.]

fix/58-bias-detector-common-phrases

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
|diagnosis  |## Plan context  |passes if the plan says what causes the bug  |required  |
|scope  |## Plan context  |look where the plan says what it will change; passes if it names each file it will change and says what it won’t touch.  |required  |
|test  |### Test evidence  |passes if it provides the steps to test the issue  |required  |
|Plan Implemented  |### Diff, ## Plan context  |passes if diff matches plan  |required  |
|Issue solved  |### Test evidence, ## Issue, ## Plan context  |Passes if testing output matches correct output from issue or from plan |required  |
|Title template| ### Title, ## Repo facts | Title for PR follows given naming template if available | required| 
(19/20)

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

pkg-03 has a golden label reject and my rubric also agrees with the verdic. The pkg fails the rubric because the diff does more than the plan outlined for the fix.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/pr-precheck/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

|Title template| ### Title, ## Repo facts | Title for PR follows given naming template if available | required|

To get here I had to specifically mention if a naming template is available because not all pr's have one.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

The test check is a simple check that may let some packages through because it only checks if 
steps to test the issue is present, not if there right or make any sense.


---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/pr-precheck/`.
