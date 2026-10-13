**Maintainer:** Frangel Raúl Crespo Barrera
**Last verified:** 2026-10-02
**Scope:** Windows audit rules, evidence collection, scoring, and reporting.

| Field | Current record |
|---|---|
| Status | Auditor implementation exists; exact CIS benchmark revision is not centrally pinned in the current policy. |
| Evidence | `pyproject.toml`, `rules/`, `evaluator.py`, `scoring.py`, `reporter.py`, `tests/test_evaluator.py`, `tests/test_scanner.py`, `.github/workflows/ci.yml`. |
| Standard | Record the exact CIS benchmark and Windows edition/version before publishing a compliance result. |
| IEC 62443 | No rule-to-SR crosswalk is maintained. CIS rule results do not establish IEC FR/SR coverage or an SL-T. |
| Verification | `pytest -q`; review the rule-to-evidence mapping for each benchmark revision. |
| Owner | Repository owner maintains the benchmark mapping. |
| Limitations | Auditor output is not CIS certification. The evaluator currently handles regex and file existence checks; bundled exact-value and numeric-comparison forms are not fully evaluated and may fall through as passing. Do not use summary scores as compliance findings until rule semantics are verified. |

A result must be traceable from CIS recommendation to auditor rule, collected evidence, and reported status. Do not commit machine credentials, domain secrets, or production inventories.

The bundled Windows checks may provide evidence for a Windows component within a broader IACS assessment, but they are not an IEC 62443-3-3 assessment of that system. Verify every rule's condition syntax and collected evidence before relying on its reported status.
