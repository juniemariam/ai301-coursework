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

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/46


**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
Every required check passes for all three → all accept. Ranking by the fit profile (Python-comfortable; wants small, well-scoped work; avoid deep framework internals and front-end):

1. #46 — ingestion benchmark — Best fit: single Python file (tests/benchmarks/test_ingestion_performance.py), pure pytest-benchmark work, most self-contained, lightest internals burden (call the ingestion entrypoint, assert timing). No UI.
2. #51 — CI migration validation — Bounded and lowest effort (5–7h), but the work is devops/YAML + a bash script rather than Python, so it's off the student's language strength.
3. #23 — end-to-end agent test — Python, but explicitly requires deep familiarity with the agent orchestrator internals (stub every tool, mock LLM, full plan→execute→synthesize lifecycle) and the highest effort (6–9h) — the "deep framework internals" the profile asks to avoid.

Note: none is the bug fix the student prefers — all three are "add tests/CI" enhancements — but #46 is the closest fit.

[
{
"item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/46",
"checks": [
{"name": "Maintainer alive", "grade": "pass", "evidence": "Last 5 commits by human Aburke225, newest 2026-09-16 (within 90 days of 2026-09-20)"},
{"name": "Repo actively used", "grade": "pass", "evidence": "archived:false; last push 2026-09-16 (within 180 days)"},
{"name": "Bounded newcomer scope", "grade": "pass", "evidence": "One concrete change: add a pytest-benchmark test in one file tests/benchmarks/test_ingestion_performance.py"},
{"name": "Issue unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, timeline has only labeled events (no linked PRs)"},
{"name": "Contribution policy compatible", "grade": "pass", "evidence": "No CONTRIBUTING/AI policy file found; silence passes"},
{"name": "Maintainer responsiveness", "grade": "unclear", "evidence": "0 comments on the issue; no first-response sample (preferred, non-gating)"},
{"name": "Adoption scale", "grade": "fail", "evidence": "1 star and no releases (preferred, non-gating)"}
],
"verdict": "accept"
},
{
"item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/51",
"checks": [
{"name": "Maintainer alive", "grade": "pass", "evidence": "Last 5 commits by human Aburke225, newest 2026-09-16 (within 90 days of 2026-09-20)"},
{"name": "Repo actively used", "grade": "pass", "evidence": "archived:false; last push 2026-09-16 (within 180 days)"},
{"name": "Bounded newcomer scope", "grade": "pass", "evidence": "One concrete change: add a CI migration-validation step across two enumerated files (.github/workflows/ci.yml, scripts/validate_migrations.sh)"},
{"name": "Issue unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, timeline has only labeled events (no linked PRs)"},
{"name": "Contribution policy compatible", "grade": "pass", "evidence": "No CONTRIBUTING/AI policy file found; silence passes"},
{"name": "Maintainer responsiveness", "grade": "unclear", "evidence": "0 comments on the issue; no first-response sample (preferred, non-gating)"},
{"name": "Adoption scale", "grade": "fail", "evidence": "1 star and no releases (preferred, non-gating)"}
],
"verdict": "accept"
},
{
"item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/23",
"checks": [
{"name": "Maintainer alive", "grade": "pass", "evidence": "Last 5 commits by human Aburke225, newest 2026-09-16 (within 90 days of 2026-09-20)"},
{"name": "Repo actively used", "grade": "pass", "evidence": "archived:false; last push 2026-09-16 (within 180 days)"},
{"name": "Bounded newcomer scope", "grade": "pass", "evidence": "One concrete change: add an integration test in one file tests/integration/test_agent_orchestrator.py using stubbed tools + mock LLM"},
{"name": "Issue unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments, timeline has only labeled events (no linked PRs)"},
{"name": "Contribution policy compatible", "grade": "pass", "evidence": "No CONTRIBUTING/AI policy file found; silence passes"},
{"name": "Maintainer responsiveness", "grade": "unclear", "evidence": "0 comments on the issue; no first-response sample (preferred, non-gating)"},
{"name": "Adoption scale", "grade": "fail", "evidence": "1 star and no releases (preferred, non-gating)"}
],
"verdict": "accept"
}
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

1. First full run (20 issues, --workers 1): agreement 18/20 scored items (bar: 18/20: PASS). Categories: claimed 4/4, clear-accept 7/8, dead-repo 3/3, policy 1/1, scope 3/4. Two disagreements: issue-15 (gold reject, graded accept) and issue-19 (gold accept, graded reject on Bounded newcomer scope).

**Issue analysis**


issue-19: My rubric rejected this issue because the "Bounded newcomer scope" check graded it as fail. The gold label says accept. My rubric's pass condition for that check requires the issue to describe "one concrete, self-contained change" and not be "an umbrella/tracking issue, an unresolved design debate, or a pure usage/support question." The model read the issue body and judged the scope as too broad or unclear for a newcomer, triggering a reject. However, the gold label considers it an acceptable first issue, which suggests my scope check's language is still slightly too strict on what counts as "bounded" — the issue likely describes a reasonable piece of work that the model over-interpreted as too complex. This is one of the 4 genuinely arguable scope calls in the eval set.

**Check rationale**

Bounded newcomer scope" check, quoted as it is currently written in my rubric.md:

| Bounded newcomer scope | Issue body + comment thread | Issue describes one concrete, self-contained change -- even if it touches multiple explicitly enumerated files/pages, as long as they all serve that one described change; is NOT an umbrella/tracking issue, an unresolved design debate, or a pure usage/support question | required |

I wrote it this way because the evidence guide's Family 3 says to grade the size of the work being asked for, not the polish of the writeup. The original wording ("one concrete, self-contained change") was flipping on multi-file documentation issues like issue-01, where the model sometimes read "touches 4 files" as "not self-contained." Adding the clause "even if it touches multiple explicitly enumerated files/pages, as long as they all serve that one described change" stabilized issue-01 from flipping between accept and reject across runs.

**Trade-offs**

The multi-file clause I added stabilized issue-01 (which flipped between accept and reject before the change), but it did not fix issue-19, which the model still sometimes rejects on scope. The check gives up precision on genuinely ambiguous scope calls: by being more permissive about multi-file work, it could let through an issue that looks bounded on paper but is actually sprawling in practice. I accept this trade-off because the alternative (stricter wording) was causing false rejections on clearly bounded multi-file tasks like documentation updates, and 18/20 clears the bar even with issue-19 as a miss.
---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. I picked #46 because it's straight Python — just writing a pytest-benchmark test in one file. Python is what I'm most comfortable with, and the task felt small enough that I could actually finish it without getting lost in some huge codebase. The other two were either not Python (#51 was mostly YAML/bash) or way too deep into the framework internals (#23 wanted me to mock out the entire agent pipeline).
2. My rubric caught the important stuff — the repo is active with commits from just a few days ago, nobody's claimed any of these issues, and there's no policy blocking AI-assisted work. What it couldn't tell me is that none of these three were bug fixes, which is what I'd have preferred. I had to make that call myself, and #46 felt like the closest thing to regular Python coding out of the bunch.
3. I don't think claiming will be a problem since it's a Path Review repo where multiple students can work on the same issue. Right now there are zero comments on it. The only thing I'm a little unsure about is pytest-benchmark since I haven't used it before, but it seems like something I can pick up pretty quickly from the docs.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
