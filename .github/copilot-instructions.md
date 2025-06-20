
## General Principles
- Write code that is **readable, maintainable, and well-structured.**
- When writing Python code, follow the **coding style guide** below.
- Keep the code **simple and concise** while ensuring clarity-**avoid over-engineering.** 
- Use English for comments and documentation, ensuring they are clear and helpful.
- When writing git commit messages, follow the **git commit message conventions** below.

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


## Git Commit Message Conventions
- use **English** for commit messages. 
- Check branch name to identify the issue number and add it in the footer.
- 採用 Conventional Commits 標準： 
```
<type>(<scope>): <主旨描述> 
- <詳細描述>               # 選填
- <footer>                # 選填，如關聯的 issue
```
- 各項描述：
  - **type**（必填）：  
    - **feat** : 新增功能；用於「引入新功能」相關的變更。
    - **fix** : 修補錯誤；用於「修正程式錯誤」或「修復問題」的變更。  
    - **docs** : 文件；如更新 README、註解，不影響程式。  
    - **style** : 程式格式；如排版、縮排，不改程式行為。  
    - **refactor** : 重構；如優化程式結構，不新增功能，也不改變既有行為。  
    - **test** : 測試；如新增或修改單元／整合測試。  
    - **chore** : 雜務；包含 CI 設定、腳本更新等，非 src 核心程式邏輯。 
    - **release** : 發版；指打標籤、更新版本號等，適用於從 develop 合併至 main。
  - **scope**（選填）：影響範圍，如 `auth`、`ui`、`api` 等。
  - **主旨描述**：一句話精簡描述；英文開頭統一小寫。
  - **詳細描述**:（選填）：針對主旨的補充說明。
  - **footer**: 關聯的 issue、任務編號等。
  - 範例： 
```
feat(auth): 新增 JWT 重新整理 Token 端點 
<空行>
 - 重構 Token 服務以支援刷新功能 
 - 增加單元與整合測試 
<空行>
issues #456
```