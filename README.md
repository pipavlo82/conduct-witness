# Conduct evidence reproduction

Weekly recomputation operated by pipavlo82 using published HORIZON SHIELD verifier code and pinned fixtures. Runs Mondays at 05:41 UTC (GitHub scheduling can be delayed), or manually from Actions.

Checks NENRIN self-tests, MUSUBI run0002 and self-tests, and Python/JavaScript A2A fixture and localhost end-to-end checks. Each run uploads receipt.json and full logs for 90 days. A separate job attests a successful receipt under this repository's identity.

This is reproduction of upstream implementations, not an independently implemented semantic verifier, a trust endorsement, or admission to a witness quorum. An attestation identifies workflow provenance; the receipt records check outcomes.

No daily witness workflow, witness private key, GitHub secret, or external witness submission is configured. Existing signed-walk records and keys are unchanged.

## Inputs and provenance

Derived from ogasurfproject-jpg/conduct-witness-template at 817913c54d6679e5aab1bb287c989651dea9d6c3.
HORIZON SHIELD fixture/SDK source: d9b3075928ab0ef41f1a9b6b6970887c18b4fb44.
Published verifiers: nenrin-verify 0.3.0 and a2a-sdk 1.2.1.
All Python dependencies are fixed in requirements.lock with wheel SHA-256 values, targeting CPython 3.12 on Linux x86_64.

Adaptations: omit setup and daily walk, retain full logs, hash-lock dependencies, pin action commits, disable checkout credentials, and isolate attestation permissions from verifier execution. reproduce.sh otherwise preserves upstream receipt/check semantics.
Dependency or source updates require a new reviewed commit; old receipts remain tied to their original run.

Run locally on compatible Linux with Python 3.12, Node 22 and bash:
install requirements.lock using pip --require-hashes --only-binary=:all:,
checkout the pinned HORIZON SHIELD source into upstream, then run bash reproduce.sh.

## Approval verification lane (2026-10-05)

The original nenrin-verify 0.3.0 and pinned JavaScript/A2A checks remain unchanged. A separate clean environment installs nenrin-verify 0.4.5 from requirements-approval.lock and runs settle_v1_10 --selftest, all 22 MUSUBI module self-tests, and the frozen run0002 recomputation. All eight check groups must pass.

Approval package source: 7264b64f3ec39f2457b8f153ad338457e49df5ae. All 51 vendored files match that commit byte-for-byte; the two adapted top-level modules match their declared source and packaged digests. The explicit v1.10 check covers 14 groups including pinned approvers, forged approvals, cross-contract binding, replay, late approval, repeatable approval, wrong action and expiry. These are upstream synthetic checks, not a complete independent audit or a live two-party contract.

A trial upgrading the original environment to 0.4.5 failed comparison against the older pinned JavaScript reports (run 37308946476); that failed evidence is retained. Isolating versions preserves the baseline without ignoring its failures. On Windows, the 0.4.5 self-test also encountered a canonical_v0.mjs CLI entrypoint issue; Linux approval tests passed.
