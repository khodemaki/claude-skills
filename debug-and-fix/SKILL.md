---
name: debug-and-fix
description: Find the root cause of a bug or error in HTML, CSS, JavaScript or Python code and give a minimal, targeted fix. Use this whenever the user pastes an error message, says code does not work, a layout looks wrong, a button does nothing, a script crashes, or asks "why is this happening", even if they do not use the word debug. Persian triggers include باگ، خطا، کار نمیکنه، ارور، دیباگ.
---

# Debug and fix

The goal is to find why the code fails, fix that cause with the smallest change, and make sure the fix really works.

## Steps
1. **Collect what is missing.** You need the code, the exact error text and what the user expected. Ask only for what is absent.
2. **Read the error from the top.** The first error is usually the real one; later errors often follow from it. Find the file and line it points to.
3. **Find the cause, not the symptom.** Explain in plain language why it happens, in one or two sentences.
4. **Give a targeted fix.** Show only the lines that change and say exactly where they go (file, function, which lines to replace). Return a full file only when the user asks or when most of it changes, because users integrate snippets faster and keep control of their code.
5. **Verify before answering.** Trace the failing input through your fix mentally, or run it if you can execute code. State which cases you checked. If you could not run it, say so.
6. **Tell them how to confirm.** One concrete action: what to click, run or look for.

## Common causes to check first

### HTML, CSS, JavaScript
- Script runs before the DOM exists. Use `defer`, or place the script at the end of the body.
- Selector does not match (typo, wrong id or class, element added later).
- `undefined` from async code: a value is used before a promise resolves. Use `await` or `.then`.
- Event handlers lost after re-rendering. Use event delegation.
- `this` has the wrong value inside callbacks. Use arrow functions.
- CSS: specificity conflicts, flex or grid children overflowing (`min-width: 0`), `z-index` that does nothing without a positioned element, cached old stylesheet (hard refresh).
- Look at the browser console and the Network tab first.

### Python
- `IndentationError` and mixed tabs and spaces.
- Mutable default arguments such as `def f(x, items=[])`.
- Off-by-one errors in ranges and slices.
- Wrong import path or running the file from the wrong folder.
- File encoding: open text files with `encoding="utf-8"`, especially for Persian text.
- Packages installed in a different environment than the one running the script.

## Answer format
**Cause:** one or two sentences.
**Fix:** the snippet and where it goes.
**Why it works:** one sentence.
**Check:** how to confirm.

## Language
Reply in the user's language. Keep code, error messages, file names and button names in code formatting on their own lines so right-to-left text does not scramble them.
