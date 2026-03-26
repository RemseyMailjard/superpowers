---
name: unit-testing
description: "Create, improve, and run unit tests. Use for: adding missing coverage, writing new tests for functions/modules, preventing regressions, refactoring safely. Keywords: unit test, tests, coverage, jest, vitest, pytest, xunit, junit, mocking, assertions."
argument-hint: "What code to test (file/function) + language/tooling constraints (Node/Python/.NET/Java) + desired behaviors/edge cases"
user-invocable: true
---

# Unit Testing

## What This Skill Does

- Adds or updates unit tests for a specific piece of code (function/module/class)
- Chooses a minimal, appropriate test runner for the repo and language
- Produces tests that are readable, deterministic, and runnable in CI/local

## When to Use

- You changed logic and want regression protection
- You need a failing test that reproduces a bug
- You want to refactor with confidence
- You want coverage on edge cases and input validation

## Guardrails

- Prefer testing **pure logic** over UI wiring.
- Avoid flaky tests: no real network, time, randomness, or shared global state unless controlled.
- Prefer small, behavior-focused tests over large integration tests.
- Don’t introduce heavy tooling unless needed for unit tests.

## Procedure

### 1) Scope the Unit

1. Identify the **unit under test** (one function/class/module).
2. Write down expected behaviors as bullet points:
   - Happy path
   - Edge cases (empty/null/invalid, boundaries)
   - Error handling
3. Identify external dependencies that should be mocked (time, IO, randomness, HTTP).

### 2) Pick the Test Approach

- **If the unit is pure logic**: test it directly (no DOM, no network).
- **If it touches the DOM**: isolate logic from DOM where possible, then test logic; for unavoidable DOM usage, use a DOM test environment (e.g., JSDOM).
- **If it depends on time**: inject a clock or mock timers.
- **If it depends on randomness**: inject a RNG or stub the random function.

### 3) Choose/Set Up a Test Runner (Minimal)

Pick the smallest fit based on the repo’s language/ecosystem:

- **JavaScript/TypeScript (Node)**
  - Prefer **Vitest** for modern projects, or **Jest** where already standard.
  - Add a `test` script and a `tests/` folder.
  - If modules are browser-only, consider extracting testable logic into a module that runs under Node.

- **Python**
  - Prefer **pytest**.
  - Add `pytest` to the environment and a `tests/` folder.

- **.NET**
  - Prefer **xUnit** (or existing test framework in the solution).

- **Java**
  - Prefer **JUnit 5**.

If the repo already has a test runner/config, **reuse it**.

### 4) Write the Tests (AAA)

For each behavior:

1. **Arrange**: set up inputs and mocks
2. **Act**: call the unit
3. **Assert**: verify outputs and side effects

Guidelines:

- Use descriptive test names: `it('returns X when Y')`.
- Assert one behavior per test when possible.
- Prefer explicit values over snapshots.
- Avoid asserting implementation details (private fields, internal calls) unless necessary.

### 5) Add Edge Cases + Negative Tests

Minimum recommended additions:

- Boundary values
- Empty/undefined/null where applicable
- Invalid inputs should throw/return an error consistently

### 6) Run + Validate

- Run the narrowest test selection first, then the full suite.
- Ensure tests are deterministic and don’t depend on local machine state.

## Completion Checklist

- Tests fail before the fix (when writing a regression test) and pass after
- No new flakiness (time/network randomness controlled)
- Tests are readable and maintainable
- Clear command to run tests exists (`npm test`, `pytest`, `dotnet test`, `mvn test`)

## Repo-Specific Notes (Static Sites)

If this repo is a static site (HTML/CSS/JS):

- Prefer extracting logic into small functions (e.g., `src/` or existing `app.js` helpers)
- Unit test those helpers under Node (Vitest/Jest)
- Keep DOM rendering tests minimal; focus on output strings/structures and input validation
