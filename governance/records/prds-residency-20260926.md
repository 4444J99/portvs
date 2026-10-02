# PRDS source residency, installed control capabilities

Supersedes permanent control-source pins in the 2026-09-24 residency decision.
Explicit `workload-pin` rows now require an immutable repository ID and reason.
The five private workload repositories remain protected by the standing recovery
exclusion; their names and paths must not be introduced into this public manifest.
Wiring their sealed declarations
into manifest consumption remains an open E2 dependency, not completed coverage.
Missing pins require managed acquisition; bootstrap cannot clone them.

Limen, Domus, and PORTVS source are remote-default catalog entries. Their installed
control capabilities must remain available. This desired residency does not make
current copies eligible for deletion: active worktrees, shared stores, native
agent state, chezmoi source, and loaded runtime consumers retain their sources
until dependency detachment is verified under Domus #397. Every actual retirement
still requires Limen's fresh ownership and preservation evidence. A custody_ref
in this manifest is a locator, never a remote preservation receipt.

No existing repository, compatibility link, runtime, or active worktree is moved
by this change. The bootstrap's existing preserve/rehome guard remains in force.
Protected workload copies outside canonical paths remain protected active work; this
manifest change is not permission to retire them. Repository restructuring is
separate from residency and is not a prerequisite for safe inactive retirement.

Owner: https://github.com/4444J99/portvs/issues/14
Dependency: https://github.com/4444J99/domus-genoma/issues/397
