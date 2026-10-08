---
name: test-fastapi
description: Create or extend pytest tests for Python FastAPI endpoints. Use when asked to test routes, request validation, authentication, or API responses in a FastAPI application.
---

# Test FastAPI endpoints

Create focused endpoint tests using the application's existing pytest conventions.

1. Inspect the requested routes, dependencies, app factory, existing fixtures, and package configuration. Reuse the project's Python environment, dependency manager, and test layout.
2. Use `fastapi.testclient.TestClient` for ordinary synchronous pytest tests. Use it as a context manager when application lifespan setup or teardown is needed. If tests must await asynchronous resources, follow existing async fixtures and HTTPX client conventions, including lifespan management where required.
3. Cover the successful response and relevant error cases, such as invalid payloads, missing resources, and authorization failures. Assert status codes and meaningful response fields based on the intended API contract.
4. Isolate external services and database state with existing fixtures or test doubles. Override FastAPI dependencies using `app.dependency_overrides` where appropriate; restore the previous overrides during fixture teardown so tests cannot affect one another. Do not connect tests to production services.
5. Keep tests deterministic and independent. Use fresh test data or transaction rollback, avoid sleeps, and keep production code changes within the user's requested scope.
6. Run the focused tests using the project's configured command, for example `python -m pytest tests/test_items.py`. Confirm tests were collected and executed. Diagnose failures without weakening assertions; report missing dependencies or environment blockers as unverified execution.

Finish with the tests added, API behaviors covered, command used, and results.

For client usage, see the [official FastAPI testing guide](https://fastapi.tiangolo.com/tutorial/testing/). For dependency overrides, see [testing dependencies](https://fastapi.tiangolo.com/advanced/testing-dependencies/).
