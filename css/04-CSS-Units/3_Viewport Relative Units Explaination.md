### Explanation of the HTML:

1. **`.full-width` (Using `vw`)**:

   - The element’s width is set to `100vw`, meaning it will always span the full width of the viewport.
   - The background color and border are added for visibility.

2. **`.full-height` (Using `vh`)**:

   - The element’s height is set to `100vh`, meaning it will always span the full height of the viewport.
   - The background color and border are added for visibility.

3. **`.responsive-square` (Using `vmin`)**:

   - The element’s width and height are set to `50vmin`, meaning it will always be a square that scales based on the smaller dimension of the viewport (width or height).
   - The text is vertically centered using `line-height: 50vmin`.

4. **`.large-text` (Using `vmax`)**:
   - The font size is set to `10vmax`, meaning it will scale based on the larger dimension of the viewport (width or height).
   - The background color and border are added for visibility.

---

### How to Test:

1. Copy the code into an HTML file (e.g., `index.html`).
2. Open the file in a browser to see the examples in action.
3. Resize the browser window to observe how the elements behave:
   - The `.full-width` element will always span the full width of the viewport.
   - The `.full-height` element will always span the full height of the viewport.
   - The `.responsive-square` will remain a square, scaling with the smaller dimension of the viewport.
   - The `.large-text` font size will scale with the larger dimension of the viewport.

This example demonstrates how to use **viewport-relative units** (`vw`, `vh`, `vmin`, `vmax`) in real-world scenarios. Let me know if you need further clarification! 😊
