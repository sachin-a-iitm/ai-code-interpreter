# Actual validation results — 2026-10-11

- Python syntax compilation: PASSED for main.py, worker.py, test_main.py, verify_live.py.
- Full pytest run on Python 3.14: blocked at collection (exit 2), one ImportError. macOS refused mmap of pydantic_core native extension with errno=1. No application tests ran.
- Retried outside tool sandbox and after local signing: same collection failure.
- Full pytest run on Python 3.13: blocked at collection (exit 2), same native extension loading error. No application tests ran.
- Linux CI on Python 3.11.17: 22 passed, 1 deprecation warning in 3.48s.
- Linux CI on Python 3.13.16: 22 passed, 1 deprecation warning in 3.69s.
- Verified run: https://github.com/sachin-a-iitm/ai-code-interpreter/actions/runs/38094853286 . Tests include actual restricted Linux workers, concurrency, timeouts, filesystem/network/process denial, and mocked LLM parsing.
- Docker/Linux sandbox tests: not run; Docker is not installed here.
- Live public HTTP requests: not run; no deployed service exists yet.

Do not interpret collection failure as test success. The test suite must pass on a supported Linux host, and live execution must work on Render before submitting a URL.
