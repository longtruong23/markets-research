# Generic project continuity

## Preserve durable state

Keep the objective, full agreed scope, settled and pending decisions, tasks and dependencies, artifact identities, evidence scopes, tool observations, issue attempts, and next actions in versioned project records. Keep detailed source and logs outside the active prompt and retrieve them when relevant.

One coordinator publishes a current pointer to an immutable checkpoint after validation. Workers write separate result files. Checkpoints carry state, an event, a derived brief, an integrity manifest, and a parent reference. Compare the expected current revision before publishing. Preserve superseded evidence instead of editing historical claims.

## Resume deliberately

After a context reset or interruption, read the current checkpoint and validate its history. Reconcile actual worker/executor liveness and artifact availability before duplicating work. A stored RUNNING field is not live-process evidence. Historical acceptance applies only to its artifact and scope. Missing input, not-run, failed, reported-pass and verified-pass are distinct states.

A seed is a one-time starting record, never a substitute for newer state. Unknown attempt totals stay unknown. Do not reset counters by changing a session, model, worker or issue alias.

## Verify the mechanism

Exercise stale-revision rejection, event idempotency, interrupted publication, missing or corrupted ancestors, changed artifact identity, context budget limits, and read-only resume. Then separately test the real agent's new-session integration on its actual operating system. Offline helper checks do not certify that integration or product correctness.

## Keep permissions separate

Context preserves approval history but does not issue credentials or revive expired authority. Any external side effect must use the current authorized execution path. An uncertain earlier effect must be reconciled before repetition.

## Keep operation small

Reuse the existing coordinator and reporter. Update records on meaningful work events and before planned handoff; keep reports to deltas. Add hooks, a database, embeddings or additional schedulers only for a demonstrated gap. Public copies remain documentation-only.
