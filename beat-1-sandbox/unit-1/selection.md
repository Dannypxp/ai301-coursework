# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

[The individual Path Review issue page. A link to the repository or the issue list
does not satisfy this field.]

'https://github.com/codepath/pathreview-ai301-fa26-s3/issues/29'

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
paste the output here, including the closing JSON block

{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/29",
  "checks": [
    {"name": "Repo Merge", "grade": "pass", "evidence": "most recent commit 2026-09-16, 5 days before today (2026-09-21)"},
    {"name": "Maintainer Reply", "grade": "fail", "evidence": "no comments/replies from anyone on #29, #62, #73, #67, #57, #69, or #68 (preferred check, does not gate verdict)"},
    {"name": "Other Active Issues", "grade": "pass", "evidence": "12+ open issues, all opened 2026-09-10 to 2026-09-16, commits as recent as 2026-09-16"},
    {"name": "AI Usage", "grade": "pass", "evidence": "no CONTRIBUTING.md, AI_POLICY.md, or AGENTS.md found in repo root or .github/ — no policy stated"},
    {"name": "goal", "grade": "pass", "evidence": "single bounded goal (red-team test suite + CI hook on safety/), named files, 7-10hr estimate"},
    {"name": "branches", "grade": "pass", "evidence": "linked PRs: none (0 closed-unmerged, well under 2); issue is a single request, not a list of other issue numbers"},
    {"name": "Assignee", "grade": "pass", "evidence": "assignees: none"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

Change Log

|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 2 weeks| Preferred | (11/20)
 ->

|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 3 weeks| Required | (13/20)

++
| AI Usage | contribution policy | Allows Any AI usage in the Policy Statement| Required | (10/20)

| AI Usage | contribution policy | Allows Any AI usage in the Policy Statement| Required | (10/20)
->
| AI Usage | contribution policy | does not state an outright ban on AI usage in policy| Required | (8/10)

|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 3 weeks| Required| (8/10)
->
|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 6 months| Required| (12/20)

++
| info | issue, steps to reproduce | Explains the issue and how to replicate | Required | (11/20)

| info | issue, steps to reproduce | Explains the issue and how to replicate | Required | (11/20)
->
| info | issue, steps to reproduce | Issue is written, good first-issue label | Required | (9/20)

| info | issue, steps to reproduce | Issue is written, good first-issue label | Required | (9/20)
->
| info | issue, steps to reproduce, description | Bug is written, Scope isnt too vast for beginners | Required | (11/20)

| info | issue, steps to reproduce, description | Bug is written, Scope isnt too vast for beginners | Required | (11/20)
->
| info | issue, steps to reproduce, description | goal / objective is written down and doesnt have unmerged branches older than 6 months  | Required | (10/20)

| info | issue, steps to reproduce, description | goal / objective is written down and doesnt have unmerged branches older than 6 months  | Required | (10/20)
->
| info | issue, steps to reproduce, description | goal / objective is written down and doesnt have unmerged branches older than 6 months and mutiple issues on the same request  | Required | (16/20)

++
| Assignee | assignees | reject if a person is already Assigned to the issue | required | (12/20)

|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 6 months| Required| (12/20)
->
|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 6 months| preferred| (13/ 20)

++
|branches | ssue, steps to reproduce, description |  doesnt have unmerged branches older than 6 months and mutiple issues on the same request | Required | (13/20)

|branches | ssue, steps to reproduce, description |  doesnt have unmerged branches older than 6 months and mutiple issues on the same request | Required | (13/20)
->
|branches | linked PRs; issue body | fewer than 2 closed-and-unmerged linked PRs, and the issue does not itself list or reference multiple other issue numbers as sub-items | Required | (18/20)


**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

item      gold    verdict  agree  note
issue-01  accept  accept   yes    

My rubric agreed with the golden decision because the issue is a fresh bug with a reponsive maintainer showing clear signs of recent activity.


**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

| Assignee | assignees | reject if a person is already Assigned to the issue | required |

The resoning behind this check is to firmly reject an issue that already is assigned to a person. The issue can satisfy all the checks but if its already assigned, it cannot be completed by me.

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]
---

No trade of with the check because it makes one clean check for an asignee, before the check was implemented other issues were passing even though a person was assigned to the issue

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
   The issue fits my cybersecurity interest and is around 10 hours long which isnt too bad on time.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
   The verdict identified an active repo correctly with a very recent merge but could not weight the subject of cybersecurity the issue focuesed on.
3. The anticipated difficulty in claiming it.]
   The difficulty in claiming the issue shouldnt be too bad because it is tier 3 and takes around 10 hours and is a specializzed topic

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
