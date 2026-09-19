---
name: code-structure
description: Use when repeated operational logic is causing inconsistency or when a feature needs a clean boundary between product rules and reusable mechanics. Do not invoke for one-off code merely to create abstraction.
---

# Code structure

## Principle

Keep product/domain rules close to the flow that owns them. Extract reusable operational mechanics only when reuse or inconsistency creates a real reason.

## Extract when

- the same operational behavior exists in multiple callers;
- fixes repeatedly have to be copied between flows;
- provider/SDK mechanics are leaking into multiple domain paths;
- a shared operation needs one reliable implementation.

## Keep local when

- the logic is used once;
- the abstraction would hide a simple flow;
- future reuse is speculative;
- extraction would enlarge a small approved task without solving a present problem.

## Boundary test

Ask:

**Does this code decide what the product should do, or how a reusable operation is performed?**

- Product policy, authorization, state transitions, and user-facing failure decisions usually stay with the domain flow.
- Reusable provider calls, file operations, parsing, transport, or repeatable mechanics may belong in a shared service/helper.

## Extraction method

1. Make current behavior clear.
2. Identify repeated mechanics.
3. Extract the smallest reusable block.
4. Give it explicit inputs and structured outputs.
5. Replace one caller.
6. Verify.
7. Migrate other callers only when useful.

Avoid god services, hidden global state, and abstractions that own domain policy accidentally.
