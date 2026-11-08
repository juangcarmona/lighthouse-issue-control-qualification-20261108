# Tasks

These tasks are a future implementation plan, not permission to execute. Begin only after separate authorization. All tasks remain unchecked. See `design.md` for decisions, review cases and evidence handling; there are no blocking design questions.

## 1. Establish the Read-only Reference Trail

- [ ] 1.1 Review README authority text, installed router/worker boundaries and issue #1's existing source request/receipt links; record the original correlation and which router receipt, worker run/attempt and validated-result hops are available. Verify each available hop refers to the same original request, mark absent or ambiguous hops unknown, and make no new requests or credential changes (AC2; evidence stays outside the product diff).

## 2. Write and Review the Compact README Section

- [ ] 2.1 Add a short developer-facing receipt sequence distinguishing recorded intent, source admission, separately confirmed worker execution and validated assessment; verify the recorded-only, admitted-without-result and complete-trail cases in `design.md`, including that a validated assessment may be blocked or failed and a green workflow alone does not prove a passed assessment (AC1).
- [ ] 2.2 Add the issue #1 starting reference and explain following existing original-request router/dispatch, confirmed run/attempt and validated-result references; verify the complete-trail and missing-history cases using the findings from 1.1, with no fabricated links, unrelated runs or ordinary-comment substitution (AC2).
- [ ] 2.3 Add a concise uncertainty caution; verify admitted-without-result, missing/ambiguous history, failed-worker plus unrelated-success, and publication/installation-only cases keep unknown outcomes unknown and failures failed, without treating publication as resolution or recommending resubmission (AC3).
- [ ] 2.4 Preserve the existing fixture description and authority limits; review the full README for developer audience, compactness, stage-only Refine/Propose, and no implied implementation, merge, release or deployment authority. Inspect its rendered preview for readable steps, caution text and link presentation, and record visual-review findings outside the product diff (AC4).

## 3. Final Documentation Integration Review

- [ ] 3.1 Review the complete implementation diff against AC1-AC4 and recorded source-link findings; run `git diff --check` and compare changed paths with the actual implementation base, including uncommitted changes if present. Verify only `README.md` changes in the product diff, existing proposal artifacts remain separate, and there are no dependency, credential, application or workflow changes; retain the command results and review-case evidence for owner review (AC4 and overall Definition of Done).

## Workflow follow-up

- The host checks proposal file boundaries, runs pinned OpenSpec strict validation and publishes the proposal candidate. This engine has not run or completed those host checks.
- The repository owner reviews the proposal and decides whether to accept it or request revisions; acceptance does not itself authorize implementation.
- Any later implementation or integration requires its own authority and current-head review. No merge, archive, release or deployment is authorized here.
