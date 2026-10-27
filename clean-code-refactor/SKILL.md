---
name: clean-code-refactor
description: Clean up, simplify and restructure working HTML, CSS, JavaScript or Python code without changing what it does, with clear explanations of each change. Use this whenever the user asks to clean, improve, simplify, organize, shorten, optimize or make code more readable or professional, or says the code is messy or too long, even if the code already works. Persian triggers include تمیز کردن کد، مرتب کن، بهینه کن، ریفکتور.
---

# Clean code and refactor

Refactoring means improving structure while behavior stays identical. Working code is valuable, so protect it.

## Principles
- **Behavior first.** Do not change what the program does unless the user asks. If you spot a real bug, mention it separately instead of silently changing it.
- **Match the project.** Follow the user's existing naming and style unless it is clearly harmful.
- **Do not over-engineer.** A small script does not need classes, patterns or new files. Prefer the simplest structure that reads well.
- **Small, explainable changes.** For each important change say what it was and why it is better, in one line.
- **Ask before big moves.** Splitting a file into many files or changing the architecture needs the user's agreement.

## What to look for
Across languages: unclear names, duplicated code, long functions doing several jobs, magic numbers, dead code, deep nesting (use early returns), comments that repeat the code instead of explaining why.

### JavaScript
`const` and `let` instead of `var`, small functions, no unnecessary globals, template literals, optional chaining, event delegation instead of many listeners, `async`/`await` with try/catch.

### CSS
Custom properties for colors and spacing, consistent class naming, remove unused rules, group related rules, mobile-first media queries, logical properties for RTL support.

### HTML
Semantic elements (`header`, `main`, `nav`, `section`, `footer`), alt text on images, one `h1`, labels tied to inputs.

### Python
PEP 8 naming, f-strings, `pathlib` for paths, `with` for files, small functions, `if __name__ == "__main__":`, clear exceptions instead of bare `except`.

## Output
1. A short summary of what you changed and what stayed the same.
2. The improved code. For a large file, show the changed parts as snippets with their location, unless the user asks for the whole file.
3. A list of optional next improvements you did not apply.

## Verify
Re-read your result against the original and confirm the inputs and outputs still match. Run it if you can. Say plainly what you could not test.
