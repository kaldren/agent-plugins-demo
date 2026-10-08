# python

An Agent Plugins package for testing Python FastAPI applications. Current version: **1.0.0**.

## Skills

| Skill | Purpose |
| --- | --- |
| [test-fastapi](skills/test-fastapi/SKILL.md) | Create or extend pytest endpoint tests covering responses, request validation, and authentication. |

The skill follows existing fixtures and package conventions, uses FastAPI's test client where appropriate, and isolates external dependencies and test state.

## Install

Install **python** from the **agent-plugins-demo** marketplace. The repository contains multiple plugins, so use the marketplace to select this package. See the [repository installation and migration guide](https://github.com/kaldren/agent-plugins-demo#install-in-vs-code).

## Use

Open your FastAPI project and ask the agent:

> Use test-fastapi to test the items endpoint, including successful requests and invalid payloads.

> Use test-fastapi to add tests for protected routes using the existing authentication fixtures.

Running tests requires the project's Python environment, pytest, FastAPI, and the test client dependencies used by the project. The skill runs focused tests and reports results or environment blockers.

## Versioning

This plugin's release version lives in [plugin.json](plugin.json) and is independent of the .NET plugin. When releasing changes, update this version and its matching marketplace entry. See the [repository update guide](https://github.com/kaldren/agent-plugins-demo#independent-versions-and-updates).

## License

MIT. See [LICENSE](LICENSE).
