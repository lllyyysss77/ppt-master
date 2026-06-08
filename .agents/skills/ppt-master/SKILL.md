```markdown
# ppt-master Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `ppt-master` Python codebase. You'll learn how to structure files, write imports and exports, follow commit message standards, and understand the project's approach to testing. This guide is ideal for contributors aiming for consistency and maintainability in their code.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `slide_generator.py`, `data_parser.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import format_title
    from . import constants
    ```

### Export Style
- Use **named exports** (explicitly define what is exported).
  - Example:
    ```python
    __all__ = ['generate_presentation', 'parse_data']
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `fix` prefix for bug fixes.
- Keep commit messages concise (average ~48 characters).
  - Example:
    ```
    fix: correct slide numbering in output
    ```

## Workflows

### Making a Code Change
**Trigger:** When you need to update or fix code.
**Command:** `/make-change`

1. Create a new branch for your change.
2. Make edits following the coding conventions.
3. Add or update relevant tests (see Testing Patterns).
4. Commit using the conventional commit style (e.g., `fix: ...`).
5. Push your branch and open a pull request.

### Running Tests
**Trigger:** Before submitting code or after making changes.
**Command:** `/run-tests`

1. Identify test files (pattern: `*.test.*`).
2. Run the tests using your preferred Python test runner (e.g., `pytest`, `unittest`).
   - Example:
     ```
     pytest
     ```
3. Ensure all tests pass before submitting your code.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `slide_generator.test.py`).
- The specific test framework is not defined; use standard Python test frameworks like `unittest` or `pytest`.
- Place test files alongside the modules they test or in a dedicated `tests/` directory.
- Example test file:
  ```python
  # slide_generator.test.py
  import unittest
  from .slide_generator import generate_presentation

  class TestSlideGenerator(unittest.TestCase):
      def test_generate_presentation(self):
          result = generate_presentation(['Title'])
          self.assertIn('Title', result)
  ```

## Commands
| Command       | Purpose                                   |
|---------------|-------------------------------------------|
| /make-change  | Start the process for making a code change|
| /run-tests    | Run all tests in the codebase             |
```