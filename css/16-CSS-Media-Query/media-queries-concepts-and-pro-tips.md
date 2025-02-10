# Logical Operators in Media Queries

Media queries can use logical operators to combine or modify conditions.

## `and` Operator (Both conditions must be true)

**Example:** Apply styles only when the screen width is at least `768px` and in landscape mode.

```css
@media (min-width: 768px) and (orientation: landscape) {
  body {
    background-color: lightblue;
  }
}
```

This will only apply the styles if **both conditions** are met.

## `,` (OR) Operator (Any condition can be true)

**Example:** Apply styles if the screen is less than `600px` wide OR if the device doesn’t support hover (like a touchscreen).

```css
@media (max-width: 600px), (hover: none) {
  body {
    background-color: pink;
  }
}
```

If either condition is true, the styles will be applied.

## `not` Operator (Negation)

**Example:** Apply styles to devices that don’t support color displays.

```css
@media not (color) {
  body {
    background-color: black;
    color: white;
  }
}
```

This means the styles will only apply on black-and-white devices.

---

# Breakpoint Strategy

## Mobile-First Approach (Recommended)

Start with styles for small screens and add styles for larger screens.

```css
/* Default (Mobile) */
body {
  font-size: 14px;
}

/* Tablet */
@media (min-width: 768px) {
  body {
    font-size: 16px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  body {
    font-size: 18px;
  }
}
```

This ensures that mobile users get a lightweight experience by default.

## Desktop-First Approach

Start with styles for large screens and adjust for smaller screens.

```css
/* Default (Desktop) */
body {
  font-size: 18px;
}

/* Tablet */
@media (max-width: 1023px) {
  body {
    font-size: 16px;
  }
}

/* Mobile */
@media (max-width: 767px) {
  body {
    font-size: 14px;
  }
}
```

This approach is less efficient, as mobile users must download unnecessary styles.

---

# Units Matter

## Use `em` Instead of `px` for Accessibility

```css
@media (min-width: 48em) {
  /* 768px @ 16px base font-size */
  body {
    background-color: lightgray;
  }
}
```

## Use Viewport Units (`vw`, `vh`)

```css
@media (height > 600px) and (width > 1000px) {
  body {
    background-color: gold;
  }
}
```

---

# Modern Syntax

## CSS4 Range Comparisons (New!)

```css
@media (600px <= width <= 1200px) {
  body {
    background-color: green;
  }
}
```

---

# Performance Tips

## Group Related Queries

```css
/* Good */
@media (min-width: 768px) {
  .a {
    color: red;
  }
  .b {
    color: blue;
  }
}
```

## Limit External Stylesheets

```html
<!-- Only load this stylesheet for desktop users -->
<link rel="stylesheet" href="desktop.css" media="(min-width: 1024px)" />
```

---

# Accessibility

## Reduce Motion for Sensitive Users

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
  }
}
```

## Support High Contrast Mode

```css
@media (prefers-contrast: high) {
  :root {
    --text: black;
    --bg: white;
  }
}
```

---

# Common Pitfalls

## Over-qualifying Selectors

Instead of:

```css
div.header#main-nav {
  color: white;
}
```

Use:

```css
.header-nav {
  color: white;
}
```

## Z-Index Battles & Specificity Issues

Stick to a consistent naming convention like BEM (Block Element Modifier).

---

# Future-Proofing

## Container Queries (New Feature)

```css
.card {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    background-color: lightcoral;
  }
}
```

## Layer Media Queries

```css
@layer mobile {
  @media (max-width: 767px) {
    body {
      background-color: yellow;
    }
  }
}
```

---

# Testing Tools

## 1️⃣ Chrome DevTools Device Mode

Simulate different devices using DevTools (F12 → Toggle Device Toolbar).

## 2️⃣ `window.matchMedia()` in JavaScript

```js
const mediaQuery = window.matchMedia("(max-width: 600px)");

mediaQuery.addEventListener("change", (e) => {
  if (e.matches) {
    console.log("Screen is small!");
  } else {
    console.log("Screen is big!");
  }
});
```

## 3️⃣ Cross-browser Testing

Use tools like BrowserStack to ensure your styles work on all devices.

---

# When NOT to Use Media Queries

## Use Flexbox/Grid Instead

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}
```

## CSS Custom Properties

```css
:root {
  --columns: 1;
}
@media (min-width: 768px) {
  --columns: 2;
}
.grid {
  grid-template-columns: repeat(var(--columns), 1fr);
}
```

---

# Pro Tip: Use Sass Mixins

```scss
@mixin tablet {
  @media (min-width: 768px) and (max-width: 1023px) {
    @content;
  }
}

.header {
  @include tablet {
    padding: 2rem;
  }
}
```

---

# Final Thought

Use fewer media queries and more intrinsic design! 🎯
