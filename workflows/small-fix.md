# Small fix workflow

Use for bounded bugs, tiny enhancements, and narrow regressions.

```text
Emmanuel approval
    ->
Minimal Change Engineer
    ->
Code Reviewer when non-trivial
    ->
Reality Checker
    ->
Emmanuel review
```

## Steps

1. Reproduce or understand the defect.
2. Read nearby code and current project rules.
3. Define the smallest safe correction.
4. Avoid unrelated refactors.
5. Implement.
6. Run the smallest relevant verification.
7. Report PASS, FAIL, or UNVERIFIED.

Do not turn a fix into an architecture project.
