# Licensing scope

The Apache License, Version 2.0, reproduced in [LICENSE](LICENSE), applies to
Pavlo-authored repository material within the scope below, to the extent Pavlo
owns or is authorized to license the relevant rights.

Copyright 2026 Pavlo Tvardovskyi

Existing third-party copyright, license, patent, attribution and trademark
notices remain applicable. For mixed or adapted material, the new grant covers
only Pavlo's original additions. Imported source, external contributions,
quoted specifications, captures and other third-party material are not
relicensed by this grant. Inclusion in this repository or a missing license
does not itself supply permission. Existing grants are not withdrawn or narrowed.

| Material | Applicable boundary |
| --- | --- |
| Pavlo's original README prose, repository/operator configuration, dependency-lock compilation and original workflow/reproduction adaptations | Apache-2.0 for Pavlo's original contributions only. |
| Upstream-derived portions of `reproduce.sh` and any retained template portions of `.github/workflows/reproduce.yml` or configuration | Derived from `ogasurfproject-jpg/conduct-witness-template` at `817913c54d6679e5aab1bb287c989651dea9d6c3`, as recorded in README. Original template rights remain applicable; this new root license does not supply missing permission or relicense the original template. |
| Verifiers and packages named by `requirements.lock` and `requirements-approval.lock` | Their original package terms apply. Package wheels/source are not bundled in this repository; hashes, versions and upstream author rights remain unchanged. |
| HORIZON SHIELD fixtures/SDK and approval source identified in README/workflow | Separate source pins `d9b3075928ab0ef41f1a9b6b6970887c18b4fb44` and `7264b64f3ec39f2457b8f153ad338457e49df5ae`; no grant for those sources is made here and no source was fetched during this cleanup. |
| Past or future receipt/log/attestation artifacts | Captured source data and embedded third-party content retain their applicable rights. A workflow attestation identifies provenance, not copyright ownership or a new upstream license. No historical artifact is changed. |

The detailed adaptation boundary in README remains authoritative. This owner
decision does not turn upstream checks into independently authored verifiers.
All seven pre-existing files, dependency hashes, action/source pins and scheduled
reproduction semantics are unchanged. The syntax-only check does not execute
`reproduce.sh`, install packages, call providers or create witness evidence.
