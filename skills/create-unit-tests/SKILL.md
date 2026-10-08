---
name: create-unit-tests
description: Create or extend unit tests for .NET and C# code. Use when asked to test a class, method, or behavior with xUnit, NUnit, or MSTest.
---

# Create .NET unit tests

Create focused tests for the requested behavior, following the repository's existing test conventions.

1. Read the target code and nearby tests. Inspect project files, `global.json`, and shared build or package settings to identify the SDK, target framework, test framework, and assertion or mocking libraries.
2. Reuse the existing test project and libraries. If no test project exists, create a small one using the user's chosen framework; default to xUnit when no preference is given. Match the production target framework, add a project reference to the code under test, and include the test project in the existing solution. Follow existing package version policies.
3. Cover the normal case and relevant boundaries, invalid inputs, or exceptions. Derive expected results from the intended contract; when the implementation conflicts with that contract, report the discrepancy instead of encoding the bug as expected behavior.
4. Write readable tests using Arrange, Act, Assert and descriptive names such as `Method_Scenario_ExpectedResult`. Use parameterized tests for related input cases. Assert observable outcomes rather than private implementation details.
5. Keep tests independent and deterministic. Replace external network, database, clock, or filesystem dependencies with existing abstractions and test doubles where needed. Await asynchronous operations; avoid sleeps and shared mutable state. Keep production changes outside the requested scope unless needed and authorized.
6. Run the relevant test project with `dotnet test path/to/Project.Tests.csproj`, using the repository's runner options if configured. Confirm the new tests are discovered and executed. Fix failures introduced by the tests and report unrelated failures separately. If the SDK, restore, or another prerequisite blocks execution, state what could not be verified.

Finish by summarizing the tests added, the behaviors covered, and the test command and result.
