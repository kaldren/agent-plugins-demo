# dotnet

An Agent Plugins package for creating, running, and reviewing .NET unit tests. Current version: **1.3.0**.

## Skills

| Skill | Purpose |
| --- | --- |
| [create-unit-tests](skills/create-unit-tests/SKILL.md) | Create or extend tests using the project's xUnit, NUnit, or MSTest conventions. |
| [run-unit-tests](skills/run-unit-tests/SKILL.md) | Execute existing tests, summarize results, and diagnose failures. |
| [review-unit-tests](skills/review-unit-tests/SKILL.md) | Review test correctness, meaningful coverage, and reliability. |

## Install

Install **dotnet** from the **agent-plugins-demo** marketplace. The repository contains multiple plugins, so use the marketplace to select this package. See the [repository installation and migration guide](https://github.com/kaldren/agent-plugins-demo#install-in-vs-code).

## Use

Open your .NET project and ask the agent:

> Use create-unit-tests to test OrderService, following the existing test framework and covering valid and invalid inputs.

> Use run-unit-tests to run the unit tests and summarize failures.

> Use review-unit-tests to review OrderService tests for missed regressions and reliability issues.

Running tests requires a compatible .NET SDK and the project's test dependencies. The skills inspect existing project conventions before choosing test tools or commands.

## Versioning

This plugin's release version lives in [plugin.json](plugin.json) and is independent of the Python plugin. When releasing changes, update this version and its matching marketplace entry. See the [repository update guide](https://github.com/kaldren/agent-plugins-demo#independent-versions-and-updates).

## License

MIT. See [LICENSE](LICENSE).
