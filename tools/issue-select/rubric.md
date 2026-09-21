# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer alive | Last 5 default-branch commit dates (repo-facts block / commit list) | At least one of the last 5 commits is by a human (not a `[bot]` account merging alone) and dated within 90 days of the capture/today date | required |
| Repo actively used | Archived flag + last push to any branch | `archived` is false AND last push to any branch is within 180 days | required |
| Bounded newcomer scope | Issue body + comment thread | Issue describes one concrete, self-contained change -- even if it touches multiple explicitly enumerated files/pages, as long as they all serve that one described change; is NOT an umbrella/tracking issue, an unresolved design debate, or a pure usage/support question | required |
| Issue unclaimed | Assignees field, linked PRs, claim comments in thread | No assignee is set, AND no open linked PR exists, AND no claim comment shows ongoing active work with no abandonment signal | required |
| Contribution policy compatible | CONTRIBUTING.md / AI policy line in repo-facts block | No outright ban on AI-assisted contributions (disclosure or human-review conditions are fine, not a fail) | required |
| Maintainer responsiveness | Maintainer first-response sample | Median first response from an Owner/Member/Collaborator is within 30 days | preferred |
| Adoption scale | Star count, latest release recency | Repo has meaningful adoption: 50+ stars OR a release within the last 12 months | preferred |

## Verdict rule

Accept if and only if every `required` check grades `pass`. Any `required`
check that grades `fail` or `unclear` rejects the issue. `preferred` checks
never change the verdict — they only rank accepted issues (higher grade
on more preferred checks ranks higher). Treat `unclear` on a required
check as `fail`: if I cannot verify one of these five, I should not take
the issue as a first contribution.