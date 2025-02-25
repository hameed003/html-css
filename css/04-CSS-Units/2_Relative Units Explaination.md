### Explanation of the HTML:

1. **`.parent` and `.child` (Using `em`)**:

   - The `.parent` element has a font size of `20px`.
   - The `.child` element uses `em` units:
     - `font-size: 1.5em` → `1.5 × 20px = 30px`.
     - `padding: 0.5em` → `0.5 × 20px = 10px`.

2. **`.header` (Using `rem`)**:

   - The root (`<html>`) font size is set to `16px`.
   - The `.header` element uses `rem` units:
     - `font-size: 2rem` → `2 × 16px = 32px`.
     - `margin-bottom: 1rem` → `1 × 16px = 16px`.

3. **`.container` (Using `%`)**:
   - The `.container` element uses percentage units:
     - `width: 80%` → 80% of the parent's width.
     - `height: 50%` → 50% of the parent's height.

---

### How to Test:

1. Copy the code into an HTML file (e.g., `index.html`).
2. Open the file in a browser to see the examples in action.
3. Resize the browser window to observe how the `.container` element adjusts its size based on the parent's dimensions.

This example demonstrates how to use **relative units** (`em`, `rem`, `%`) in real-world scenarios. Let me know if you need further clarification! 😊
