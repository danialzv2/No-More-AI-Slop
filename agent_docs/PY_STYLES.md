# Python Code Writing Guidelines

Use this guide with the shared writing rules in [AGENTS.md](../AGENTS.md). Write straightforward, readable code that a data scientist can easily understand and maintain.
Prefer practical code over unnecessary structure or boilerplate.

## Simplicity
- Use the simplest implementation that meets the requirements.
- Do not overengineer or add functionality that was not requested.
- Prefer plain Python and existing libraries over new abstractions.
- Use functions for meaningful or reusable logic; do not create helpers for trivial one-time operations.
- Do not create classes, wrappers, configuration objects, or extra files without a clear reason.
- Follow existing project conventions when they make sense.

## Python Style
- Use clear, natural variable and function names.
- Keep the code easy to read from top to bottom.
- Prefer explicit steps over clever one-liners or deeply nested expressions.
- Use intermediate variables when they make complex logic easier to follow.
- Do not add type annotations to every local variable. Use type hints when useful, especially at function boundaries.
- Keep short function signatures on one line; wrap longer signatures when needed.
- Format dictionaries and collections so their contents are easy to scan.
- Keep imports and dependencies minimal.

## Comments and Documentation
- Prefer short `#` comments over triple-quoted (`""" """`) docstrings.
- Put a brief `#` comment above a function to explain its purpose, especially when the name alone is not enough.
- Put a brief `#` comment before a meaningful block of connected steps, such as filtering files, cleaning data, or validating records.
- Comments should help someone understand the purpose of the code, not narrate every operation.
- Use comments to clarify business rules, assumptions, and non-obvious decisions.
- Use simple, natural wording. Avoid long explanations and formal boilerplate.
- Do not comment every line or add headings for tiny, obvious steps.
- Do not add docstrings by default. Use them only when explicitly requested or required by an existing project convention or public API.
- Keep comments accurate when changing the code.

Example:

```python
# Find registered files in the monthly archive folders.
found = []
for path in archive_root.glob("*/*/*"):
    if not path.is_file():
        continue

    month = forecast_files.submission_month_from_folder(path.parent.name)
    status, _ = forecast_files.match_source(path.name, registry)

    if month is not None and status == "MATCHED":
        found.append((path, f"{month:%Y-%m}"))
```

## Functions and Structure
- Keep each function focused on a meaningful task.
- Keep simple transformations simple, including when working with pandas.
- Do not split a short, readable operation across multiple unnecessary functions.
- Avoid design patterns and extra layers unless the project genuinely needs them.

## Data Science and Notebooks
- Keep data processing in a clear, sequential flow.
- Use normal pandas operations where appropriate.
- Keep notebooks runnable from top to bottom without hidden state.
- Use brief Markdown headings or `#` comments for major analysis stages when helpful.
- Show useful intermediate results without excessive output.
- Do not create utility modules for simple notebook-only operations.

## Reliability
- Validate external inputs and required data fields where failures matter.
- Let Python and existing libraries raise their own errors when that is sufficient.
- Use `ValueError`, `RuntimeError`, or other exceptions when they protect meaningful assumptions, data integrity, or unsafe operations.
- Do not add unnecessary `try/except` blocks or validation for every variable.
- Prefer simple, direct error handling over excessive defensive programming.
- Do not silently suppress exceptions or remove important safety checks just to shorten code.
- Preserve correctness, security, and data integrity.
- Add focused tests for meaningful behavior changes; avoid tests that only repeat implementation details.

## Modifying Existing Code
- Read the relevant implementation before editing.
- Make the smallest reasonable change and reuse existing code where appropriate.
- Preserve existing behavior unless a change is requested.
- Do not refactor unrelated code or create unnecessary files.
- Remove redundant code introduced by the change.
- Verify the affected behavior and state clearly what was not tested.

## Priority
When approaches are equally correct and readable, prefer fewer moving parts.
Do not trade away clarity, correctness, or necessary validation merely to reduce line count.
