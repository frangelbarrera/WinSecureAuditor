**Maintainer:** Frangel Raúl Crespo Barrera
**Last verified:** 2026-10-02
**Scope:** Windows audit rules, evidence collection, scoring, and reporting.

| Field | Current record |
|---|---|
| Status | Auditor implementation exists; exact CIS benchmark revision is not centrally pinned in the current policy. |
| Evidence | `pyproject.toml`, `rules/`, `evaluator.py`, `scoring.py`, `reporter.py`, `tests/test_evaluator.py`, `tests/test_scanner.py`, `.github/workflows/ci.yml`. |
| Standard | Record the exact CIS benchmark and Windows edition/version before publishing a compliance result. |
| Verification | `pytest -q`; review the rule-to-evidence mapping for each benchmark revision. |
| Owner | Repository owner maintains the benchmark mapping. |
| Limitations | Auditor output is an assessment aid, not CIS certification; synthetic or sanitized fixtures only. |

A result must be traceable from CIS recommendation to auditor rule, collected evidence, and reported status. Do not commit machine credentials, domain secrets, or production inventories.
