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

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/53

**Verdict output**

Live-mode run on three candidates (#60, #53, #56), 2026-09-22. My skill's verdict
on the issue I chose, **#53, is `accept`** — it is the top-ranked accepted
candidate. Full output below, ending with the fenced JSON block.

````
## Repo facts (captured 2026-09-22)

- **archived:** no
- **last 5 default-branch commits:** Sep 16, 2026 × 3 (Aburke225 + "claude" co-author); Aug 24, 2026 × 2 (Aburke225 solo). Newest is 6 days old.
- **CONTRIBUTING.md:** exists at `docs/CONTRIBUTING.md`; silent on AI use.
- **Aburke225** is the maintainer: authors every commit and opened all three issues.

---

## Issue #60 — Faithfulness checker crashes on `text: None`

- `repo-not-archived` — **pass**: no archived banner
- `maintainer-still-shipping` — **pass**: last commit Sep 16, 2026 (6 days ago)
- `bounded-single-change` — **pass**: one method (`FaithfulnessChecker.check`), one named failing test, reproduction shown
- `spec-is-settled` — **pass**: maintainer filed it with a concrete repro and expected fix
- `nobody-already-on-it` — **fail**: PR #74 is **open** and linked (opened Sep 21, 2026 by student nianiiier). The Path Review house rule only ignores *claim comments*; the rubric's "no linked PR is in the open state" still applies as written.
- `ai-assisted-work-allowed` — **pass**: CONTRIBUTING.md is silent on AI use
- `newcomer-signposting` (preferred) — **pass**: `good first issue` label, names file/method, reproduction included
- `maintainer-answers-issues` (preferred) — **unclear**: recent issues show no visible comments in the listing sample

**Verdict: reject** — blocked by open linked PR #74.

## Issue #53 — PII scrubber misses parenthesized US phone numbers

- `repo-not-archived` — **pass**
- `maintainer-still-shipping` — **pass**
- `bounded-single-change` — **pass**: one regex in one module; the four listed tests all exercise the same fix
- `spec-is-settled` — **pass**: maintainer-authored, concrete repro, wanted behavior stated
- `nobody-already-on-it` — **pass**: assignees none, no linked PRs, no claim comments
- `ai-assisted-work-allowed` — **pass**: silence
- `newcomer-signposting` (preferred) — **pass**: `good first issue` label, body names behavior and four failing tests
- `maintainer-answers-issues` (preferred) — **unclear**

**Verdict: accept**

## Issue #56 — Structural chunker drops documents with no headings

- `repo-not-archived` — **pass**
- `maintainer-still-shipping` — **pass**
- `bounded-single-change` — **pass**: single method behavior in one file, named failing test
- `spec-is-settled` — **pass**: maintainer-authored bug report with repro; two suggested fixes ("single block or fallback strategy") are suggested steps inside one bug, which the rubric explicitly allows
- `nobody-already-on-it` — **pass**: assignees none, no linked PRs, no claim comments
- `ai-assisted-work-allowed` — **pass**
- `newcomer-signposting` (preferred) — **pass**: `good first issue` label, names file path and failing test path
- `maintainer-answers-issues` (preferred) — **unclear**

**Verdict: accept**

---

## Ranked read-out (accepted first, in fit order)

1. **#53 (PII phone regex)** — best fit: a self-contained regex fix in one Python module with four named failing tests. Smallest, tightest scope of the three; the fix location is essentially pointed to.
2. **#56 (structural chunker)** — accepted, Python bug with a repro, but slightly less bounded because the fix requires picking between two behaviors the opener sketched (single-block vs. fallback strategy).
3. **#60 (faithfulness `text: None`)** — rejected: PR #74 is already open against it.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/53",
    "checks": [
      {"name": "repo-not-archived", "grade": "pass", "evidence": "no archived banner on repo front page"},
      {"name": "maintainer-still-shipping", "grade": "pass", "evidence": "most recent default-branch commit Sep 16, 2026, 6 days before capture date 2026-09-22"},
      {"name": "bounded-single-change", "grade": "pass", "evidence": "single phone-regex fix in PII scrubber; four listed failing tests all exercise the same behavior"},
      {"name": "spec-is-settled", "grade": "pass", "evidence": "issue opened by Aburke225 (repo's sole committer / maintainer) with concrete reproduction and stated wanted behavior"},
      {"name": "nobody-already-on-it", "grade": "pass", "evidence": "assignees: none; no linked PRs; no claim comments"},
      {"name": "ai-assisted-work-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md does not mention AI-assisted contributions; silence passes"},
      {"name": "newcomer-signposting", "grade": "pass", "evidence": "'good first issue' label present; body names failing tests and the specific input format that fails"},
      {"name": "maintainer-answers-issues", "grade": "unclear", "evidence": "recent-issues listing shows no visible comments; first-response dates not exposed by the view"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/56",
    "checks": [
      {"name": "repo-not-archived", "grade": "pass", "evidence": "no archived banner on repo front page"},
      {"name": "maintainer-still-shipping", "grade": "pass", "evidence": "most recent default-branch commit Sep 16, 2026, 6 days before capture date 2026-09-22"},
      {"name": "bounded-single-change", "grade": "pass", "evidence": "one method (StructuralChunker.chunk); reproduction shown; single named failing test tests/unit/test_structural_chunker.py::test_document_with_no_headings"},
      {"name": "spec-is-settled", "grade": "pass", "evidence": "maintainer-authored bug report with repro; two suggested implementation options ('single block or fallback strategy') are steps inside one bug, which the rubric allows"},
      {"name": "nobody-already-on-it", "grade": "pass", "evidence": "assignees: none; Development sidebar shows no linked PRs; no comments"},
      {"name": "ai-assisted-work-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md silent on AI use"},
      {"name": "newcomer-signposting", "grade": "pass", "evidence": "'good first issue' label; body names ingestion/chunking/structural_chunker.py and the failing test path"},
      {"name": "maintainer-answers-issues", "grade": "unclear", "evidence": "recent-issues listing shows no visible comments; first-response dates not exposed"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/60",
    "checks": [
      {"name": "repo-not-archived", "grade": "pass", "evidence": "no archived banner on repo front page"},
      {"name": "maintainer-still-shipping", "grade": "pass", "evidence": "most recent default-branch commit Sep 16, 2026, 6 days before capture date 2026-09-22"},
      {"name": "bounded-single-change", "grade": "pass", "evidence": "one method (FaithfulnessChecker.check); reproduction shown; single named failing test test_none_context_chunk_text"},
      {"name": "spec-is-settled", "grade": "pass", "evidence": "maintainer-authored issue with concrete reproduction and stated cause"},
      {"name": "nobody-already-on-it", "grade": "fail", "evidence": "linked PR #74 opened by student nianiiier on 2026-09-21 is in the 'open' state; Path Review house rule ignores claim comments only, not linked open PRs"},
      {"name": "ai-assisted-work-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md silent on AI use"},
      {"name": "newcomer-signposting", "grade": "pass", "evidence": "'good first issue' label; body names the specific method and failing test"},
      {"name": "maintainer-answers-issues", "grade": "unclear", "evidence": "recent-issues listing shows no visible comments; first-response dates not exposed"}
    ],
    "verdict": "reject"
  }
]
```
````

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

One run. I wrote the rubric out in full before spending any credit on it, so the
first complete run was also the last one.

1. Run 1 (full, 20 scored items) — **20/20**, bar 18/20: PASS. Per-category:
   `claimed 4/4`, `clear-accept 8/8`, `dead-repo 3/3`, `policy 1/1`, `scope 4/4`.

That is the run in `eval-run.txt`, whose agreement line reads
`agreement: 20/20 scored items  (bar: 18/20: PASS)`.

The only thing I had to fix before the run was my own launch command: I first
pointed `--rubric` at `/.claude/skills/...` with a leading slash, which resolves
to the filesystem root, and ran `run_eval.py` from the wrong directory. Neither
attempt graded anything or cost credit — the harness exited on a missing file
both times.

**Issue analysis**

**`issue-12`** (bookwyrm-social/bookwyrm#1133, "Include in-progress books in the
reading-goal progress-bar"). My rubric decided **reject**; the gold label is
**reject**; they agree.

This is the issue I find most interesting in the set, because every signal I
would have trusted on instinct points the other way. The repo is healthy —
`archived: no`, and the last default-branch commit is dated `2026-08-12`, the
same day as the capture, so `maintainer-still-shipping` passes easily. The issue
carries a `good first issue` label. `assignees: none`, `linked PRs: none`. There
is a claim comment, but jrings wrote "I've started to look at this as it seems to
be a good first issue" on `2024-09-19`, which is far more than 90 days before the
`2026-08-12` capture date, so my `nobody-already-on-it` check treats it as stale
and does not block. The ask is one bounded change to one progress bar. Five of my
six required checks pass.

It rejects on exactly one check, `ai-assisted-work-allowed`, reading the
contribution-policy line in the Repo facts block:

> "Meaningful human interaction is the whole point of BookWyrm. We do not accept
> AI-generated code or documentation. If you are unsure how something in BookWyrm
> works, please ask for help – we are keen to help other humans to understand and
> contribute to the project."

That is a refusal of the work itself, not a condition attached to it, which is the
distinction my check is written around. So the verdict rule — accept only if every
required check passes — turns a five-out-of-six issue into a reject.

I want to be honest that this check is the reason I passed the category floor
rather than a deep insight of mine. `policy` has exactly one scored issue in the
set, `issue-12`, so the floor makes that single verdict unskippable: get it wrong
and the floor is unmet no matter what the total says. I only noticed that after
the run, looking at the per-category line.

**Check rationale**

`bounded-single-change`, quoted as it currently stands in
`tools/issue-select/rubric.md`:

> | `bounded-single-change` | The issue title and body. | The body asks for one
> change that a single pull request could deliver. Fail only when the body is a
> list of separate sub-items meant to be split across many PRs — linked issue
> numbers, separate pages, a tracking or "mega" issue — or asks for the same edit
> applied across the whole codebase with no stated stopping point. A terse
> two-line body passes. Edits to several named files in one change pass. A
> maintainer's list of suspected causes or suggested implementation steps inside
> one bug report passes: grade the size of the change being asked for, not the
> polish or the length of the writeup. | required |

The whole shape of this check is the phrase **"Fail only when"**. My first
instinct was to write it the other way round — pass only when the issue is
clearly small — and I talked myself out of that, because "clearly small" is a
judgment about how an issue *reads*, and short, blunt, badly punctuated issues
are not the same thing as big ones. A two-line bug report with no formatting is
often the most bounded issue in the repo. If I had written a pass-only-when
condition, I would have been grading writing quality and calling it scope.

So instead I named the two failure shapes I can actually point at in the text and
nothing else: a body that decomposes into sub-items meant for separate PRs
(linked issue numbers, separate pages, a tracking issue), and a body that asks
for one edit repeated across the codebase with no stated stopping point. Both are
things I can quote a line for. Everything else passes by default.

The last three sentences are all guards against a specific way I saw myself about
to go wrong. "A terse two-line body passes" stops me penalizing brevity. "Edits
to several named files in one change pass" stops me reading file count as scope,
when a rename touching six files is still one change. And the clause about a
maintainer's list of suspected causes exists because a thorough bug report with
five debugging leads in it *looks* like five tasks, and it is not — it is one
task with good notes attached.

**Trade-offs**

What `bounded-single-change` gives up is **depth**. It grades how wide a request
is, and it cannot see how hard the request is, because difficulty is not
something an issue body reports about itself.

The case I accept it will miss: an issue that asks for one behavior, in one
sentence, with a clear stopping point, where delivering that behavior means
rewriting something underneath it. "Make the search results respect the user's
locale" is one change by every clause I wrote — no sub-items, no linked issues,
no codebase-wide sweep, and a terse body passes on purpose — and it could still
be a month of work for a newcomer. My check passes it. I decided that is the
right trade anyway: the alternative is guessing at implementation cost from an
issue body, and a rubric that guesses is worse than one that admits what it
cannot see. What partly covers the gap is the preferred check
`newcomer-signposting`, which rewards bodies that name the files or give
acceptance criteria. That does not change a verdict, but it pushes the issues
whose depth is visible to the top of the accepted list, which is where I
actually make the decision.

`issue-12` is the concrete proof of the limit. `bounded-single-change` passed it
— a stacked progress bar is genuinely one change — and the thread shows what the
check could not: jrings had already tried, got the data broken out, and stalled
on the frontend, with the maintainer confirming "There isn't a built-in way to do
a stacked bar." A scope check reading only the body sees a small, tidy ask. Only
the policy check rejected it, and that was for an unrelated reason.

Nothing changed elsewhere from writing it this permissively, and here is how I
know: the run scored `scope 4/4`, so all four of the issues built to test scope
judgment (`issue-05`, `issue-10`, `issue-15`, `issue-20`) still came out
`reject`, and `clear-accept 8/8`, so the permissive wording did not drag any
genuine accept into a rejection either. The two failure shapes I did name were
enough to catch every scope case in the set without a third.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

**1. Fit to my interests and to the time available.**

Python is the language I have actually written and debugged, and #53 is Python
end to end: one regex in `safety/pii_scrubber.py`. It is also the kind of work I
said in my scope profile that I want more of — a bug with a reproduction I can
run, rather than a feature where I would have to invent the requirements first.
The domain helps too. I do not need to understand how the whole RAG pipeline
fits together to know that `(555) 123-4567` is a phone number and should come
back redacted; the correctness criterion is something I can hold in my head.

On time: this is a two-week unit and I have to reproduce the bug, fix it, and
open a PR in Unit 2. A single regex with four existing failing tests is
realistically sized for that. I deliberately did not pick the most interesting
issue in the repo, I picked one I am confident I can finish.

**2. What the verdict identified correctly, and what I weighed that it could not.**

The verdict got the thing I would most likely have gotten wrong on my own. My
first choice was #60, the faithfulness-checker crash, and I would have claimed
it: it is labelled `good first issue`, it has no assignees, and it has zero
comments, so every signal I was eyeballing said it was free. My skill rejected
it, because `nobody-already-on-it` also reads linked PRs, and PR #74 — opened
the day before by another student — is sitting open against it. I had not looked
at the Development sidebar at all. That is a check earning its place: it saw a
claim that leaves no trace in the comment thread.

What I weighed that the rubric could not is the **named failing tests**. #53's
body ends with `test_us_phone_number_redaction`, `test_us_phone_formats`,
`test_detect_phone_pii`, and `test_phone_at_start_of_text` in
`tests/unit/test_pii_scrubber.py`. That means I do not have to decide when I am
done — the repo already decides for me, and I can work by running those four
tests until they pass. For a first contribution that is worth more to me than
anything else on the page, and my rubric has no check for it. The closest it
gets is `newcomer-signposting`, which rewards a body that "gives acceptance
criteria or reproduction steps," but that is a preferred check that only breaks
ties, and it cannot tell the difference between a vague repro and four test
names I can paste straight into `pytest`. If I extend the rubric later, "the
issue names an existing test that currently fails" is the check I would add.

**3. Anticipated difficulty in claiming it.**

Low, and lower than for #60. As of 2026-09-22 #53 has no assignees, no linked
PRs, and zero comments, twelve days after it was opened — and #74 is the only
open PR in the entire repository, so nobody is quietly working on #53 either.
The Path Review house rules say classmates' claim comments do not block an issue
anyway, and that credit attaches to the PR I open rather than to whether it
merges, so even if someone claims it alongside me it costs neither of us
anything.

The real risk is not the claim, it is that #53 is an attractive issue for the
same reasons I picked it, and #60 just showed me how fast that turns into an
open PR — one appeared overnight. So the plan is to claim early in Unit 2 rather
than sit on it. If it is taken by then, #56 (the structural chunker) is my
fallback: my skill also accepted it, and it ranked second on fit.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
