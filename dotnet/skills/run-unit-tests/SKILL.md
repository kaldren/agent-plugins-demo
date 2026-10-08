---
name: run-unit-tests
description: Run existing .NET unit tests and summarize results or diagnose failures. Use when asked to execute C# tests, rerun a failing test, or check a .NET test suite.
---

# Run .NET unit tests

Execute the requested tests and report actionable results.

1. Inspect the repository's test instructions, `global.json`, test project files, and CI configuration. Use the configured SDK, test runner, and options. Identify the unit test projects and keep integration or end-to-end suites outside the run unless requested.
2. Run the relevant test project with `dotnet test path/to/Project.Tests.csproj`. For a specific test or class, use the configured runner's supported filtering options. Use the existing build and restore defaults unless the repository documents another workflow.
3. Confirm tests were discovered and executed; a successful command with zero matching tests does not verify the requested behavior. Capture passed, failed, and skipped counts when available.
4. For failures, inspect the assertion output and relevant test and production code. Distinguish failed assertions from build, SDK, restore, or environment problems. Rerun a focused failing test when it helps diagnose the cause; report intermittent results rather than treating a passing retry as proof of a fix.
5. When asked only to run tests, report failures and likely causes without modifying code or weakening assertions. If fixes are also requested, make focused changes and rerun the affected tests.

Finish with the commands used, test counts, important failures, and any blocked or unverified tests.
