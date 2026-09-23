# Rubric: is this a good first issue?

Seven required checks, two preferred. The required ones cover the four
families that kill first contributions — the maintainer is alive, the repo
is in use, the scope fits a newcomer, nobody else is already on it — plus
the fifth surface, whether the repo's contribution policy allows
AI-assisted work at all.

All recency thresholds are measured against the bundle's capture date in
eval mode, and against today in live mode.

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| `repo-not-archived` | The `archived:` flag on the repo line of the Repo facts block. | `archived: no`. An archived repo is read-only and cannot merge anything, so `archived: yes` fails outright. | required |
| `maintainer-still-shipping` | The dates in "last 5 default-branch commits" under Repo facts, and "last push to any branch". | The newest of the last 5 default-branch commits is dated within 90 days of the capture date. A commit authored by a bot account counts as maintainer life when it merges a human's pull request; if all 5 are bot-authored dependency bumps with no human PR behind them, fall back to "last push to any branch" and apply the same 90 days. | required |
| `bounded-single-change` | The issue title and body. | The body asks for one change that a single pull request could deliver. Fail only when the body is a list of separate sub-items meant to be split across many PRs — linked issue numbers, separate pages, a tracking or "mega" issue — or asks for the same edit applied across the whole codebase with no stated stopping point. A terse two-line body passes. Edits to several named files in one change pass. A maintainer's list of suspected causes or suggested implementation steps inside one bug report passes: grade the size of the change being asked for, not the polish or the length of the writeup. | required |
| `spec-is-settled` | The issue body, the `author_association` on each comment in the thread, and the `linked PRs:` line under Repo facts. | Someone with OWNER, MEMBER, COLLABORATOR, or CONTRIBUTOR association has stated what the finished change should do — by filing the issue themselves, by specifying the wanted behavior in the body, or by settling the approach in the thread — and no later comment reopens that question. Fail when the thread still holds competing proposals that no maintainer comment resolved, when two or more linked PRs are closed unmerged (abandoned attempts on a problem harder than it looks), or when the wanted behavior is asserted only by a NONE-association opener and no maintainer has endorsed it. | required |
| `nobody-already-on-it` | `this issue: assignees:` and `linked PRs:` under Repo facts, plus claim comments in the thread with their dates. | All three hold: `assignees: none`; no linked PR is in the `open` state; and no claim comment ("working on this", "can I work on this", "I'd like to take this") is dated within 90 days of the capture date. A claim older than 90 days is stale and does not block. A closed-unmerged linked PR is an abandoned attempt, not a live claim. A bot's inactivity-warning comment does not clear a claim that is still standing as an assignee or an open PR. | required |
| `ai-assisted-work-allowed` | The "contribution policy" line under Repo facts; in live mode, `CONTRIBUTING.md` and the docs it links out to, any `AI_POLICY.md`, and PR-template disclosure checkboxes. | No outright ban on AI-assisted contributions. Wording that refuses the work itself — "we do not accept AI-generated code or documentation" — fails. Conditions pass: disclose your AI use, personally understand and test the change, get human review before submitting. Discouragement, or a rule that closes AI output submitted *without* human review, is a condition and passes. Silence, or no CONTRIBUTING.md at all, passes. | required |
| `newcomer-signposting` | The issue's labels and body. | At least one of: a `good first issue`, `help wanted`, or `easy` label; the body names the files, directories, or components to touch; the body gives acceptance criteria or reproduction steps. | preferred |
| `maintainer-answers-issues` | The "maintainer first-response sample" under Repo facts. | At least one issue in the sample drew a first owner, member, or collaborator comment within 30 days. Never a reject on its own: healthy repos routinely leave most issues unanswered while shipping code daily, so commit activity carries the liveness verdict and this only separates accepted candidates. | preferred |

## Verdict rule

Accept if and only if every `required` check is graded `pass`. A single
required check graded `fail` rejects the issue. A required check graded
`unclear` counts as a fail: a first issue whose evidence you cannot verify
is not a first issue you should take.

Preferred checks never change the verdict. Report their grades, and use
them to rank the issues that were accepted: among accepted candidates,
prefer the one passing more preferred checks, `newcomer-signposting`
first.
