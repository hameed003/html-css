CSS (Cascading Style Sheets) provides a variety of units to define lengths, sizes, and distances. These units can be categorized into **absolute units**, **relative units**, and **viewport-relative units**. Below is an explanation of each type with examples:

---

### 1. **Absolute Units**

Absolute units are fixed and do not depend on the size of the parent element or the viewport. They are best used for print styles or when precise sizing is required.

- **`px` (Pixels)**:

  - 1px is equal to one dot on the screen.
  - Example: `font-size: 16px;` sets the font size to 16 pixels.

- **`in` (Inches)**:

  - 1in is equal to 2.54cm.
  - Example: `width: 2in;` sets the width to 2 inches.

- **`cm` (Centimeters)**:

  - Example: `height: 5cm;` sets the height to 5 centimeters.

- **`mm` (Millimeters)**:

  - Example: `padding: 10mm;` sets the padding to 10 millimeters.

- **`pt` (Points)**:

  - 1pt is equal to 1/72 of an inch.
  - Example: `font-size: 12pt;` sets the font size to 12 points.

- **`pc` (Picas)**:
  - 1pc is equal to 12 points.
  - Example: `line-height: 1.5pc;` sets the line height to 1.5 picas.

#### Examples:

```css
/* Using pixels (px) */
.box {
  width: 300px; /* Fixed width of 300 pixels */
  height: 150px; /* Fixed height of 150 pixels */
  font-size: 16px; /* Font size of 16 pixels */
}

/* Using inches (in) */
.print-page {
  width: 8.5in; /* Width of 8.5 inches (standard paper size) */
  height: 11in; /* Height of 11 inches */
}

/* Using centimeters (cm) */
.margin-example {
  margin: 2cm; /* Margin of 2 centimeters */
}
```

**When to use:**

- For print styles (e.g., `in`, `cm`, `mm`).
- When you need precise control over element sizes (e.g., `px`).

---

### 2. **Relative Units**

Relative units are based on the size of another element or property. They are more flexible and responsive.

- **`em`**:

  - Relative to the font size of the parent element.
  - Example: If the parent element has a font size of `16px`, `font-size: 1.5em;` will set the font size to `24px` (1.5 × 16).

- **`rem` (Root Em)**:

  - Relative to the font size of the root (`<html>`) element.
  - Example: If the root font size is `16px`, `font-size: 2rem;` will set the font size to `32px`.

- **`%` (Percentage)**:

  - Relative to the parent element's size.
  - Example: `width: 50%;` sets the width to 50% of the parent element's width.

- **`ex`**:

  - Relative to the height of the lowercase "x" in the current font.
  - Example: `font-size: 2ex;` sets the font size to twice the height of the lowercase "x".

- **`ch`**:
  - Relative to the width of the "0" (zero) character in the current font.
  - Example: `width: 20ch;` sets the width to 20 times the width of the "0" character.

#### Examples:

```css
/* Using em */
.parent {
  font-size: 20px;
}

.child {
  font-size: 1.5em; /* 1.5 × 20px = 30px */
  padding: 0.5em; /* 0.5 × 20px = 10px */
}

/* Using rem */
html {
  font-size: 16px; /* Root font size */
}

.header {
  font-size: 2rem; /* 2 × 16px = 32px */
  margin-bottom: 1rem; /* 1 × 16px = 16px */
}

/* Using percentages (%) */
.container {
  width: 80%; /* 80% of the parent's width */
  height: 50%; /* 50% of the parent's height */
}
```

**When to use:**

- `em`: For scaling elements relative to their parent’s font size.
- `rem`: For consistent scaling relative to the root font size.
- `%`: For responsive layouts (e.g., widths, heights, margins).

---

### 3. **Viewport-Relative Units**

Viewport-relative units are based on the size of the browser's viewport (the visible area of the webpage).

- **`vw` (Viewport Width)**:

  - 1vw is equal to 1% of the viewport's width.
  - Example: `width: 50vw;` sets the width to 50% of the viewport's width.

- **`vh` (Viewport Height)**:

  - 1vh is equal to 1% of the viewport's height.
  - Example: `height: 100vh;` sets the height to 100% of the viewport's height.

- **`vmin` (Viewport Minimum)**:

  - Relative to the smaller dimension of the viewport (width or height).
  - Example: `font-size: 5vmin;` sets the font size to 5% of the [viewport's smaller dimension](https://github.com/hameed003/html-css/blob/main/css/04-CSS-Units/vmin-and-vmax.md).

- **`vmax` (Viewport Maximum)**:
  - Relative to the larger dimension of the viewport (width or height).
  - Example: `font-size: 5vmax;` sets the font size to 5% of the [viewport's larger dimension](https://github.com/hameed003/html-css/blob/main/css/04-CSS-Units/vmin-and-vmax.md).

#### Examples:

```css
/* Using vw (viewport width) */
.full-width {
  width: 100vw; /* 100% of the viewport width */
}

/* Using vh (viewport height) */
.full-height {
  height: 100vh; /* 100% of the viewport height */
}

/* Using vmin (viewport minimum) */
.responsive-square {
  width: 50vmin; /* 50% of the smaller viewport dimension */
  height: 50vmin; /* Creates a square that scales with the viewport */
}

/* Using vmax (viewport maximum) */
.large-text {
  font-size: 10vmax; /* 10% of the larger viewport dimension */
}
```

**When to use:**

- `vw`/`vh`: For full-screen layouts or scaling elements to the viewport size.
- `vmin`/`vmax`: For responsive designs that adapt to both portrait and landscape orientations.

---

### 4. **Other Units**

- **`fr` (Fractional Unit)**:

  - Used in CSS Grid layouts to divide available space into fractions.
  - Example: `grid-template-columns: 1fr 2fr;` creates two columns where the second column is twice as wide as the first.

- **`deg` (Degrees)**:

  - Used for rotations in transforms.
  - Example: `transform: rotate(45deg);` rotates an element by 45 degrees.

- **`s` (Seconds)** and **`ms` (Milliseconds)**:
  - Used for animations and transitions.
  - Example: `transition: all 0.5s;` applies a transition effect over 0.5 seconds.

#### Examples:

```css
/* Using fr (fractional unit) in CSS Grid */
.grid-container {
  display: grid;
  grid-template-columns: 1fr 2fr; /* Second column is twice as wide as the first */
}

/* Using deg (degrees) for rotations */
.rotate-box {
  transform: rotate(45deg); /* Rotates the element by 45 degrees */
}

/* Using s (seconds) and ms (milliseconds) for animations */
.fade-in {
  animation: fade 2s ease-in-out; /* Animation lasts 2 seconds */
}

@keyframes fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
```

**When to use:**

- `fr`: For dividing space in CSS Grid layouts.
- `deg`: For rotations and transformations.
- `s`/`ms`: For animations and transitions.

---

### When to Use Which Unit?

1. **Absolute Units** (`px`, `in`, `cm`, etc.):
   - Use for fixed sizes or print layouts.
2. **Relative Units** (`em`, `rem`, `%`, etc.):
   - Use for responsive designs and scaling based on parent or root elements.
3. **Viewport-Relative Units** (`vw`, `vh`, `vmin`, `vmax`):
   - Use for full-screen layouts or scaling based on the viewport size.
4. **Other Units** (`fr`, `deg`, `s`, `ms`):
   - Use for specific purposes like CSS Grid, rotations, or animations.

By combining these units effectively, you can create flexible, responsive, and visually appealing designs!
