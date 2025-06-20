
## General Principles
- Write code that is **readable, maintainable, and well-structured.**
- When writing Python code, follow the coding style guide below.
- Keep the code **simple and concise** while ensuring clarity-**avoid over-engineering.** 
- Use English for comments and documentation, ensuring they are clear and helpful.

## Coding Style Guide

###  Code Layout

- Use 4 spaces per indentation level. Never use tabs.
- Limit all lines to a maximum of 79 characters. For long docstrings or comments, wrap at 72 characters.
- Surround top-level function and class definitions with two blank lines.
- Method definitions inside a class are surrounded by a single blank line.
- End every file with a single newline.
- Use type hints for all function signatures and variable annotations.

### Import

- One import per line
- Import Order, follow this order: 
    1. Standard library imports
    2. Related third-party imports
    3. Local application/library-specific imports

- Separate groups with a blank line
- Avoid wildcard imports

### Whitespace

- Add spaces in the following situations:
  - Around operators: `a + b`, `x == y` not `a+b`, `x==y` 
  - After commas, colons, semicolons: `a, b`, `key: value` not `a,b`, `key:value` 

- Avoid extra spaces in the following situations: 
  - inside parentheses, brackets, or braces: `func(a, b)`, `[1, 2, 3]`, `{key: value}` not `func( a, b )`, `[ 1, 2, 3 ]`, `{ key: value }`

### Naming Conventions

- Modules & Packages: Lowercase, short names; underscores if it improves readability (e.g. my_module).
- Class Names: CapWords (PascalCase), e.g. MyClass.
- Function & Variable Names: lowercase_with_underscores, e.g. compute_value.
- Constants: ALL_CAPS_WITH_UNDERSCORES, e.g. MAX_OVERFLOW.
- “Internal” (non-public) names: _single_leading_underscore, e.g. _internal_helper.

### Strings & Encoding

- Single or double quotes are both fine; be consistent within a project.
- Choose the quote style that avoids backslashes in the string.
- Use f-strings (formatted string literals) for string interpolation when possible, e.g. `f"Hello, {name}"`. 

### Comments & Docstrings

- Inline Comments: Use sparingly. Begin with # , capitalized, end with a period.
- Block Comments: Indent to the same level as the code. Each line starts with #.
- Docstrings: 
  - All public modules, functions, classes, and methods should have docstrings.
  - Use triple double quotes """ for docstrings.
  - The first line should be a short summary.
  - Leave a blank line after the summary before further elaboration.
  - The docstring should describe the function's purpose, parameters, return values, and exceptions raised in every functions and methods, 
    for example:
    ```python   
    def my_function(param1: int, param2: str) -> bool:
        """
        Short summary of the function.

        Longer description of the function's purpose and behavior.

        Args:
            param1 (int): Description of the first parameter.
            param2 (str): Description of the second parameter.

        Returns:
            bool: Description of the return value.
        
        Raises:
            ValueError: If an error condition occurs.
        """
    ``` 
  

### Programming Recommendations
- Default Argument Values don’t use mutable defaults: `def f(a, items=None):` not `def f(a, items=[]):`.
- Comparisons to Singletons use `is` or `is not` when comparing with None, True, or False.
- Boolean Tests use the fact that empty sequences are falsey: `if not seq:` instead of `if len(seq) == 0`.