# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.



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


-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
|Repo Merge  | last push to any branch | Last merge under 2 month old  | Required |

|Maintainer Reply | maintainer first-response sample | Last reply by a maintainer under 6 months| preferred| 

|Other Active Issues | open issues + PRs | Other Issues are active | Required |

| AI Usage | contribution policy | does not state an outright ban on AI usage in policy | Required|

| goal | issue, steps to reproduce, description | goal / objective is written down  | Required | 

|branches | linked PRs; issue body | fewer than 2 closed-and-unmerged linked PRs, and the issue does not itself list or reference multiple other issue numbers as sub-items | Required |

| Assignee | assignees | reject if a person is already Assigned to the issue | required |



## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

accept if every required check passes; 
preferred checks never change the verdict, 
they rank accepted issues; 
unclear counts as fail.