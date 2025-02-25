### Explanation of the HTML:

1. **`.grid-container` (Using `fr`)**:

   - A grid container with two columns:
     - The first column takes up **1 fraction** of the available space.
     - The second column takes up **2 fractions** of the available space (twice as wide as the first).
   - Each grid item (`.grid-item`) is styled with a background color, border, and padding.

2. **`.rotate-box` (Using `deg`)**:

   - A box that is rotated by **45 degrees** using `transform: rotate(45deg)`.
   - The text inside the box is centered vertically using `line-height`.

3. **`.fade-in` (Using `s` and `ms`)**:
   - A box that fades in over **2 seconds** using the `fade` animation.
   - The `@keyframes` rule defines the animation, starting from `opacity: 0` (invisible) and ending at `opacity: 1` (fully visible).

---

### How to Test:

1. Copy the code into an HTML file (e.g., `index.html`).
2. Open the file in a browser to see the examples in action:
   - The grid layout will show two columns, with the second column twice as wide as the first.
   - The rotated box will appear at a 45-degree angle.
   - The fade-in box will animate from invisible to visible over 2 seconds.

This example demonstrates how to use **CSS Grid fractional units (`fr`)**, **rotations (`deg`)**, and **animations (`s`, `ms`)** in real-world scenarios. Let me know if you need further clarification! 😊
