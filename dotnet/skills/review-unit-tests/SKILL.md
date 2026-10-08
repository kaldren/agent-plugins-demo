---
name: review-unit-tests
description: Review existing .NET and C# unit tests for correctness, meaningful coverage, and reliability. Use when asked to assess tests written with xUnit, NUnit, or MSTest and identify actionable improvements.
---

# Review .NET unit tests

Assess whether the requested tests verify the intended behavior and detect realistic regressions.

1. Read the tests, the production code they exercise, and any documented requirements. Follow the repository's test framework and conventions when assessing the code.
2. Check that each test reaches its intended scenario and asserts a meaningful outcome. Look for missing assertions, incorrect expected values, and mocks that bypass the behavior under test. Identify specific regressions that could pass unnoticed rather than recommending more coverage solely to increase a percentage.
3. Compare coverage with the requested behavior. Consider relevant boundaries, invalid inputs, exception paths, and asynchronous outcomes. Distinguish unit test gaps from behavior that needs integration tests.
4. Inspect test isolation and reliability. Look for shared mutable fixtures, reliance on test ordering, real external services, uncontrolled time or randomness, sleeps, and asynchronous calls that are not awaited.
5. Prioritize findings by impact. For each actionable issue, cite the file and line, explain the missed behavior or failure risk, and suggest a focused correction. Avoid imposing stylistic preferences where existing conventions are consistent.
6. Run the affected test project when useful and feasible, following its configured runner options. Report the command and results, including tests not executed because of environment blockers. A passing test suite alone does not establish that assertions or coverage are sufficient.

For a review-only request, leave code unchanged. If fixes are also requested, make focused changes and rerun the affected tests without weakening valid assertions.

Finish with prioritized findings and verification results. If no actionable issues are found, say so and note any concrete coverage gaps or unverified behavior.
