# Proposal

## Why

Developers inspecting this qualification fixture need a short path through source receipts, not just a statement that publication, admission, execution and results differ. Issue [#1](https://github.com/juangcarmona/lighthouse-issue-control-qualification-20261108/issues/1) is ready for planning a README-only guide that prevents missing evidence from becoming an assumed success or permission to continue.

## What Changes

- Plan one compact developer-facing section in `README.md`, preserving the existing fixture description and authority limits.
- Explain recorded request, source-admitted worker and validated result, separating worker execution state from the assessment outcome. None of these evidence levels implies the next; a validated result can be blocked or failed.
- Describe a read-only trail through issue #1's existing source references, router/dispatch receipt, confirmed worker run/attempt and validated stage result when present. Keep original-request correlation and mark missing hops explicitly.
- Preserve unknown, unavailable, ambiguous and incomplete outcomes and known failed executions. Do not substitute unrelated success, ordinary comments or a new request for the original evidence.
- Preserve stage-only Refine/Propose and the absence of implementation, merge, release or deployment authority.

## Capabilities

### New Capabilities

None. This documents existing receipt semantics; it introduces no system behavior.

### Modified Capabilities

None. No existing behavior contract changes. The supplied checkout has no `openspec` directory, specifications or active OpenSpec changes. `.openspec.yaml` opts out with `skip_specs: true`; documentation review cases are in `design.md` and `tasks.md`, not invented specifications.

## Impact

The eventual product diff is limited to `README.md`. No application code, APIs, stored data, dependencies, credentials, workflows, SDK behavior or activation policy change. The proposal artifacts remain within `openspec/changes/issue-1-proposal/`; they are not an exception to the README-only product scope.

This is a planned candidate based on the [passed refinement](https://github.com/juangcarmona/lighthouse-issue-control-qualification-20261108/issues/1#issuecomment-6717279542), not accepted design or implementation permission. The host validates and publishes the candidate; the owner decides whether to accept it or request revisions. Any eventual implementation requires separate authorization.
