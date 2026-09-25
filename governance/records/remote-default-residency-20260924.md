# Remote-default repository residency checkpoint

The Workspace manifest now records five authored repositories as `remote-default`
catalog entries and keeps PORTVS, Limen, and Domus as `control-pin` infrastructure.
The bootstrap accepts an absent remote-default checkout and never clones one from
this manifest. A missing control pin remains a visible blocker for Limen-managed
acquisition. Legacy `laptop` rows retain their existing bootstrap behavior only
for older manifests; the current owner manifest has none.

Focused bootstrap verification: `python3 -m pytest -q tests/test_workspace_bootstrap.py`
passed 69 tests. The live read-only `jack.sh --plan` produced zero actions and six
blockers: three control canonical-path mismatches or unrehomed legacy sources,
and three compatibility links whose canonical targets are not yet valid. This is
not a migration or live parity receipt. Earlier checked apply/plan/verify receipts
are bound to the previous manifest digest and remain historical.

The next migration must preserve unique Git/private payloads and active leases
before moving control roots. No checkout is retired by this change.
