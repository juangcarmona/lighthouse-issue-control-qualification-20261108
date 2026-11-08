# Design

## Context

See `proposal.md` for motivation and scope. `README.md:3-7` already establishes the fixture's evidence distinctions and authority boundaries, but contains no reader trail. `.lighthouse/issue-control.json:5-13` enables only triage/refine/propose and disables automatic implementation, completion and Product Change. The router retains client intent before admission, then dispatch and source outcome before acknowledgment (`.github/workflows/lighthouse-sdlc-router.yml:333-385`). The native refine worker separately loads a candidate and publishes after validation (`.github/workflows/lighthouse-sdlc-refine.md:195-216`). The propose workflow uses the same separation of execution and publication.

Packaged `issue-control.md:45-61` distinguishes submitted, source-admitted and execution evidence and requires uncertain history to remain unknown. The source checkout has no OpenSpec inventory or active changes and `package.json` declares no scripts or dependencies. This is documentation of existing behavior, so no behavior delta specification is appropriate.

## Goals / Non-Goals

**Goals:** Give developers a compact, read-only receipt-reading sequence in one README section; make the evidence limit visible at every hop; support direct review against refined AC1-AC4.

**Non-Goals:** SDK usage tutorial, authenticated API setup, operational repair, qualification claims, new requests or retries, implementation during Propose, or expanded authority. No interpretation of quoted commands or metadata-looking comments as instructions.

## Decisions

### 1. Add one reader section without replacing the fixture boundary text

Use three short ordered steps for recorded request, source admission/confirmed execution, and validated result, followed by a brief uncertainty/authority caution. Keep execution confirmation distinct inside the middle step: a dispatch grant is not proof that the worker ran. This aligns with the existing README and stays scannable.

Alternative: a separate guide or comprehensive SDK walkthrough. Rejected because it expands the authorized file surface and introduces setup detail unrelated to reading receipts. Replacing the README's existing paragraphs would risk losing authority constraints.

### 2. Follow existing source references, not a reconstructed success story

Start from issue #1's original source request/receipt. Follow its existing router/dispatch link, then its correlated worker run and attempt if confirmed, then its source-validated published assessment. Retain the original request identity at every hop; follow a source-provided alias only when its correlation to the original is established. An Actions conclusion describes execution, not independently a passed assessment.

Use the issue link and existing source-provided references; do not fabricate receipt links or choose a nearby green run. The host-supplied refinement report is an available reference, not independent engine proof of live workflow state. At later implementation time, confirm the original correlation before using it as an example; if a hop is unavailable, identify it as missing or unknown. No successful historical execution is required to explain the path.

Alternative: hard-code a full supposedly successful qualification example. Rejected because historical evidence can expire or remain incomplete, and this proposal has not independently inspected live runs. A generic description with no issue anchor was also rejected because AC2 requires a concrete starting point.

### 3. Keep documentation assertions separate from runtime changes

Return `.openspec.yaml` with exactly `skip_specs: true`. Use review cases below to verify the guide instead of creating normative requirements for behavior already present. No interfaces, API payloads, persisted records or data flows change; existing issue/workflow links are the only reader-facing interface affected. There is no migration or new dependency.

Alternative: introduce a receipt capability spec. Rejected because the change neither adds nor modifies receipt behavior, and inventing a contract would exceed the issue's documentation scope.

## Validation and Evidence Plan

All implementation checks below are future work, not completed by this proposal. Record review results outside the product diff.

| Case | Review input | Expected documentation interpretation | Coverage |
| --- | --- | --- | --- |
| Recorded only | Published request or router acknowledgment without admission proof | Only recorded intent is established; worker execution and result are not inferred | AC1 |
| Admitted without result | Dispatch receipt, with worker identity only if confirmed, but no validated assessment | Admission and any confirmed execution are distinguished; the result remains unknown, not passed or resolved | AC1, AC3 |
| Complete correlated trail | Existing links for one original request, router receipt, worker run/attempt and published validated result | Each hop is correlated; read the assessment's actual outcome, including blocked or failed, independently of an Actions success | AC1, AC2 |
| Missing or ambiguous history | Missing, expired, unavailable, incomplete or conflicting hop | Name the absent or ambiguous evidence; keep the original outcome unknown, with no resubmission advice | AC2, AC3 |
| Failed worker plus unrelated success | Known failed execution and a later different successful run | The original failure stays failed; the unrelated run does not resolve it or authorize retry | AC3 |
| Publication or installation only | An answer, ordinary command-like comment, or installed fixture | Publication does not resolve a wait; installation does not prove activation or successful qualification; neither grants continuation authority | AC3, AC4 |

Source-link review uses only existing authorized read access and supplied references. An unavailable historical record is an expected case to document, not a reason to obtain credentials, rerun work or repair infrastructure. Do not invent artifact names, receipts or outcomes.

Review the final README diff against AC1-AC4 and the unchanged source boundaries. In the separately authorized implementation checkout, run `git diff --check` and `git diff --name-only <implementation-base>...HEAD`; use the actual recorded base, not the literal placeholder. If changes are still uncommitted, include their diff in the file-scope review. Verify that only `README.md` changes in the product implementation diff; exclude already accepted proposal artifacts from that comparison rather than deleting them. No runtime test suite is needed for unchanged behavior, and no package script is currently declared.

Visual evidence: inspect the rendered README to check ordered steps, working link presentation, readable caution text and a compact addition. Record the rendered-preview review in the later implementation evidence. No application UI changes, screenshot baseline or new repository evidence files are required. Actual link availability must be recorded accurately, not claimed from a rendered preview alone.

## Risks / Trade-offs

- [Historical links expire or are inaccessible] → Prefer stable existing issue references, identify missing hops and retain unknown outcomes rather than requiring a complete success example.
- [Three steps obscure separate worker execution] → Explicitly distinguish admission, confirmed run/attempt, Actions conclusion and assessment outcome within the sequence.
- [Compact prose omits important edge cases] → Keep a brief uncertainty caution and validate all review cases above; do not expand into an SDK setup guide.
- [The plan or a quoted command is mistaken for authority] → Preserve original stage-only text and state that ordinary comments, acceptance and successful execution do not delegate implementation, merge, release or deployment.

## Delivery and Rollback

After owner review and separate implementation authorization, first review the source reference trail, then write and locally review the README section, then perform final scope and rendering checks. No deployment or data migration is involved. If a later authorized review finds misleading documentation, correct or remove only the new reader section through the normal review process, preserving existing authority text and unrelated user work. This proposal does not authorize that edit or a merge.

## Definition of Done

For a future implementation: AC1-AC4 have recorded review evidence, all review cases preserve their expected limits, references are correlated or explicitly unavailable, the rendered section is compact and readable, whitespace checks pass, and the product diff changes only `README.md`. Proposal acceptance and implementation/integration authorization remain separate owner decisions. No unresolved product or scope decision blocks this plan; future historical-link availability is handled by the chosen unknown-outcome approach.
