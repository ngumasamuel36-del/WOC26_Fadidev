# Introduction to CSS — Styling the Web
### Fadidev Studio — Front-End Web Development Training
**Lesson 4 | CSS Basics**

---

## What We Cover Today

1. [Quick Recap & Homework Review](#1-quick-recap--homework-review)
2. [What Is CSS?](#2-what-is-css)
3. [How to Add CSS to HTML](#3-how-to-add-css-to-html)
4. [CSS Syntax](#4-css-syntax)
5. [Selectors](#5-selectors)
6. [Colors](#6-colors)
7. [Typography — Text Styling](#7-typography--text-styling)
8. [Backgrounds](#8-backgrounds)
9. [Width and Height](#9-width-and-height)
10. [The Cascade and Specificity](#10-the-cascade-and-specificity)
11. [Practice Task](#11-practice-task)
12. [Recap Questions](#12-recap-questions)
13. [Homework](#13-homework)

---

## 1. Quick Recap & Homework Review

Before we start CSS, let us review what you researched:

- What is CSS and what problem does it solve?
- What is the difference between a class and an ID in CSS?
- What does "cascading" mean in CSS?

Good. Now let us go deeper.

---

## 2. What Is CSS?

**CSS** stands for **Cascading Style Sheets**.

HTML builds the structure of a page. CSS controls how that structure **looks** — colors, fonts, sizes, spacing, layout, animations, and more.

Without CSS, every web page looks like this:

```
Black text on a white background.
Default browser fonts.
No spacing, no color, no personality.
```

With CSS, that same HTML becomes a designed, branded, professional-looking page.

### The Three Languages of the Web

| Language | Role | Analogy |
|----------|------|---------|
| **HTML** | Structure | The skeleton of a building |
| **CSS** | Appearance | The paint, furniture, and decoration |
| **JavaScript** | Behaviour | The electricity and plumbing |

### What CSS Does Not Do

Just like HTML, CSS is **not a programming language**. It cannot make decisions, run loops, or handle logic. It only describes how elements should look.

---

## 3. How to Add CSS to HTML

There are three ways to write CSS. Each has its place.

### Method 1 — Inline CSS

Written directly on the HTML element using the `style` attribute.

```html
<h1 style="color: red; font-size: 32px;">Hello World</h1>
<p style="color: gray;">This is a paragraph.</p>
```

**When to use:** Almost never. Avoid this as a habit.

**Problems:**
- Hard to maintain — you have to edit every element individually
- Mixes structure and styling in the same place
- Cannot be reused across multiple elements

### Method 2 — Internal CSS

Written inside a `<style>` tag in the `<head>` of the HTML file.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <style>
      h1 {
        color: red;
        font-size: 32px;
      }
      p {
        color: gray;
      }
    </style>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

**When to use:** For small, single-page projects or quick tests.

**Problem:** Styles only apply to this one HTML file. Not reusable across multiple pages.

### Method 3 — External CSS (The Right Way)

CSS is written in a separate `.css` file and linked to the HTML using a `<link>` tag in the `<head>`.

**index.html:**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

**style.css:**
```css
h1 {
  color: red;
  font-size: 32px;
}

p {
  color: gray;
}
```

**Why this is the right way:**
- One CSS file can style hundreds of HTML pages
- Keeps structure and styling completely separate
- Easier to maintain and update
- Browser caches the CSS file, making pages load faster

> From this point forward, we always use external CSS. Create a `style.css` file and link it to every HTML file.

---

## 4. CSS Syntax

Every CSS rule follows the same pattern:

```css
selector {
  property: value;
  property: value;
}
```

- **Selector** — targets which HTML element(s) to style
- **Property** — what aspect of the element to change (color, size, font, etc.)
- **Value** — what to set that property to
- **Declaration** — one property-value pair (e.g. `color: red;`)
- **Rule** — the full block: selector + all its declarations
- **Semicolon** — ends every declaration (never forget this)
- **Curly braces** — wrap all declarations for that selector

```css
/* This is a CSS comment */

h1 {
  color: navy;          /* text color */
  font-size: 36px;      /* text size */
  font-weight: bold;    /* text weight */
}
```

---

## 5. Selectors

Selectors are how you tell CSS which elements to style. This is one of the most important things to master in CSS.

### Element Selector

Targets all elements of a specific type.

```css
/* All h1 elements */
h1 {
  color: navy;
}

/* All paragraphs */
p {
  font-size: 16px;
}

/* All links */
a {
  color: blue;
}
```

### Class Selector

Targets any element with a specific `class` attribute. Uses a dot (`.`) prefix.

```html
<!-- HTML -->
<p class="intro">This is an intro paragraph.</p>
<p>This is a normal paragraph.</p>
<h2 class="intro">This heading also has the intro class.</h2>
```

```css
/* CSS — targets all elements with class="intro" */
.intro {
  color: darkblue;
  font-size: 18px;
}
```

**Key points about classes:**
- One element can have multiple classes: `class="intro highlight bold"`
- Multiple elements can share the same class
- Classes are reusable — use them as much as you want
- Always start with a letter, no spaces

### ID Selector

Targets a single element with a specific `id` attribute. Uses a hash (`#`) prefix.

```html
<!-- HTML -->
<h1 id="page-title">Welcome to Fadidev Studio</h1>
```

```css
/* CSS — targets the one element with id="page-title" */
#page-title {
  color: crimson;
  text-align: center;
}
```

**Key points about IDs:**
- An ID must be **unique** on the page — only one element per ID
- Use IDs sparingly in CSS — prefer classes
- IDs are mostly used for JavaScript targeting and anchor links

### Class vs ID — Summary

| | Class | ID |
|--|-------|----|
| Symbol | `.classname` | `#idname` |
| How many times | Reusable — many elements | Unique — one element only |
| Best used for | Styling groups of elements | Unique elements, JS hooks |

### Group Selector

Applies the same styles to multiple selectors at once using a comma.

```css
h1, h2, h3 {
  font-family: Georgia, serif;
  color: #333;
}

p, li {
  line-height: 1.6;
}
```

### Descendant Selector

Targets elements that are inside another element.

```html
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
</nav>

<p>
  Visit <a href="#">our website</a> for more.
</p>
```

```css
/* Only targets links inside nav — not links inside paragraphs */
nav a {
  color: white;
  text-decoration: none;
}
```

### Universal Selector

Targets every single element on the page. Used carefully.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

> This is called a **CSS reset** — one of the first things you will write in every project to remove the default spacing browsers add to elements.

### Pseudo-class Selectors

Target elements in a specific **state**.

```css
/* When the user hovers over a link */
a:hover {
  color: orange;
  text-decoration: underline;
}

/* When a link has been visited */
a:visited {
  color: purple;
}

/* The first paragraph inside any element */
p:first-child {
  font-weight: bold;
}

/* An input field that is focused (clicked into) */
input:focus {
  border-color: blue;
  outline: none;
}
```

---

## 6. Colors

CSS gives you multiple ways to define colors.

### Color by Name

CSS has 140+ named colors.

```css
h1 { color: red; }
p  { color: gray; }
nav { background-color: navy; }
```

Common named colors: `black`, `white`, `red`, `blue`, `green`, `gray`, `orange`, `pink`, `purple`, `yellow`, `crimson`, `teal`, `coral`, `salmon`, `gold`

### Hexadecimal (Hex)

The most common way to define color in real projects. A `#` followed by 6 characters representing red, green, and blue values.

```css
h1 { color: #ff0000; }       /* red */
p  { color: #333333; }       /* dark gray */
nav { background-color: #1a1a2e; }  /* dark navy */
```

```
#RRGGBB
  ||||||
  ||++++-- Blue (00 to ff)
  ++------ Green (00 to ff)
  Red (00 to ff)

#000000 = Black (all zero)
#ffffff = White (all max)
#ff0000 = Pure red
#00ff00 = Pure green
#0000ff = Pure blue
```

Shorthand hex — when each pair repeats, you can shorten it:
```css
#ff0000 → #f00   /* red */
#ffffff → #fff   /* white */
#000000 → #000   /* black */
#333333 → #333   /* dark gray */
```

### RGB

Red, Green, Blue — each value from 0 to 255.

```css
p { color: rgb(51, 51, 51); }          /* dark gray */
nav { background-color: rgb(26, 26, 46); }  /* dark navy */
```

### RGBA — RGB with Transparency

The `a` (alpha) value controls transparency: `0` = fully transparent, `1` = fully opaque.

```css
/* A semi-transparent black overlay */
.overlay {
  background-color: rgba(0, 0, 0, 0.5);
}

/* A slightly transparent blue button */
.btn {
  background-color: rgba(0, 100, 255, 0.8);
}
```

### Which to Use?

| Format | When to use |
|--------|------------|
| Named | Quick testing, very basic projects |
| Hex | Real projects — industry standard |
| RGB/RGBA | When you need transparency |

> **Tip:** Use a color picker to find hex codes. VSCode has one built in — hover over any color value and a picker appears.

---

## 7. Typography — Text Styling

### Font Size

```css
p {
  font-size: 16px;    /* pixels — most common */
  font-size: 1rem;    /* relative to root font size — better for accessibility */
  font-size: 1.2em;   /* relative to parent element's font size */
}
```

For now, use `px` — we will cover `rem` and `em` when we get to responsive design.

### Font Weight

```css
p {
  font-weight: normal;   /* default — same as 400 */
  font-weight: bold;     /* same as 700 */
  font-weight: 300;      /* light */
  font-weight: 400;      /* normal */
  font-weight: 600;      /* semi-bold */
  font-weight: 700;      /* bold */
  font-weight: 900;      /* extra bold */
}
```

### Font Style

```css
p { font-style: normal; }    /* default */
p { font-style: italic; }
```

### Font Family

Defines the typeface. Always list multiple fonts as a fallback chain.

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  font-family: Georgia, "Times New Roman", serif;
}

code {
  font-family: "Courier New", Courier, monospace;
}
```

The browser tries the first font. If it is not installed, it tries the next. The last value (`sans-serif`, `serif`, `monospace`) is a generic fallback the browser always has.

### Google Fonts — Free Web Fonts

You are not limited to system fonts. Google Fonts gives you hundreds of free, beautiful fonts.

**Step 1 — Add to your HTML `<head>`:**
```html
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
```

**Step 2 — Use in your CSS:**
```css
body {
  font-family: 'Poppins', sans-serif;
}
```

### Text Alignment

```css
h1 { text-align: center; }
p  { text-align: left; }      /* default */
.quote { text-align: right; }
.justify { text-align: justify; }  /* stretches text to fill full width */
```

### Text Decoration

```css
a { text-decoration: none; }        /* removes underline from links */
a { text-decoration: underline; }
h1 { text-decoration: line-through; }
p  { text-decoration: overline; }
```

### Text Transform

```css
h1 { text-transform: uppercase; }   /* ALL CAPS */
p  { text-transform: lowercase; }   /* all lowercase */
h2 { text-transform: capitalize; }  /* First Letter Of Each Word */
```

### Line Height

Controls the spacing between lines of text. Makes text much more readable.

```css
p {
  line-height: 1.6;   /* 1.6× the font size — standard for body text */
}
```

### Letter Spacing

```css
h1 {
  letter-spacing: 2px;    /* more space between characters */
}

.tight {
  letter-spacing: -1px;   /* less space */
}
```

### Color

```css
h1 { color: #1a1a2e; }
p  { color: #555555; }
a  { color: #0066cc; }
```

---

## 8. Backgrounds

### Background Color

```css
body {
  background-color: #f5f5f5;
}

header {
  background-color: #1a1a2e;
}

.card {
  background-color: white;
}
```

### Background Image

```css
.hero {
  background-image: url('images/banner.jpg');
}
```

### Background Size

```css
.hero {
  background-image: url('images/banner.jpg');
  background-size: cover;     /* covers the entire element — most common */
  background-size: contain;   /* fits the image inside without cropping */
  background-size: 100% 50%;  /* custom width and height */
}
```

### Background Position

```css
.hero {
  background-image: url('images/banner.jpg');
  background-size: cover;
  background-position: center;        /* centre the image */
  background-position: top left;
  background-position: center bottom;
}
```

### Background Repeat

```css
.hero {
  background-image: url('images/banner.jpg');
  background-repeat: no-repeat;   /* do not tile the image */
  background-repeat: repeat;      /* tile in both directions (default) */
  background-repeat: repeat-x;    /* tile horizontally only */
  background-repeat: repeat-y;    /* tile vertically only */
}
```

### Background Shorthand

You can combine all background properties into one line:

```css
.hero {
  background: url('images/banner.jpg') center/cover no-repeat;
}
```

---

## 9. Width and Height

```css
div {
  width: 500px;         /* fixed width in pixels */
  width: 100%;          /* full width of the parent element */
  width: 50%;           /* half the width of the parent */
  max-width: 1200px;    /* never wider than this, even on large screens */
  min-width: 300px;     /* never narrower than this */

  height: 200px;        /* fixed height */
  height: auto;         /* height adjusts to fit content (default) */
  min-height: 100vh;    /* at least the full height of the viewport */
}
```

> `vh` means **viewport height** — `100vh` is the full height of the browser window. Very useful for hero sections.

---

## 10. The Cascade and Specificity

### What Is the Cascade?

The "C" in CSS stands for **Cascading**. When multiple rules target the same element, CSS has a system to decide which one wins.

The cascade works on three factors — in order of importance:

1. **Specificity** — how specific the selector is
2. **Order** — when specificity is equal, the last rule wins
3. **Importance** — `!important` overrides everything (use sparingly)

### Specificity

Different selectors have different weights. The more specific the selector, the higher priority it has.

| Selector | Specificity Weight |
|----------|-------------------|
| Element (`h1`, `p`) | Lowest |
| Class (`.intro`) | Medium |
| ID (`#title`) | High |
| Inline style | Very high |
| `!important` | Overrides all |

```css
/* Specificity example */

p {
  color: black;       /* element selector — low specificity */
}

.intro {
  color: blue;        /* class selector — beats element */
}

#main-text {
  color: red;         /* ID selector — beats class */
}
```

```html
<!-- This paragraph will be RED because ID beats class beats element -->
<p class="intro" id="main-text">What color am I?</p>
```

### Order Matters When Specificity Is Equal

```css
p {
  color: blue;
}

p {
  color: red;   /* this wins — same specificity, but comes later */
}
```

### `!important` — Use With Caution

```css
p {
  color: blue !important;   /* this will always win, no matter what */
}

#title {
  color: red;   /* normally this would win, but !important overrides it */
}
```

> Avoid `!important` as much as possible. It makes CSS very hard to debug and maintain. If you find yourself using it often, your selector structure needs rethinking.

---

## 11. Practice Task

Style the **About Me page** you built in Lesson 2.

Create a `style.css` file and link it to your `index.html`. Apply the following:

**Layout and background:**
- Set `background-color` on the `body` to a light gray (`#f5f5f5`)
- Give the `header` a dark background color and white text
- Give the `footer` a matching dark background and white text

**Typography:**
- Link a Google Font of your choice and apply it to the `body`
- Set `font-size: 16px` and `line-height: 1.6` on `body`
- Centre the `h1` text
- Make all `h2` a different color from the body text

**Links:**
- Remove the underline from all links in the `nav`
- Change link color on hover using `:hover`

**Images:**
- Set a `width` on your profile image (e.g. `200px`)

**Classes:**
- Add a class called `highlight` to one of your paragraphs
- Style `.highlight` to have a different background color and some padding

**Bonus:**
- Add a Google Font and apply it only to headings
- Use `text-transform: uppercase` on the `nav` links
- Set a `max-width` on the main content area and centre it on the page

**Push to GitHub when done.**

---

## 12. Recap Questions

1. What does CSS stand for and what does each word mean?
2. What are the three ways to add CSS to HTML? Which is preferred and why?
3. What is the difference between a class selector and an ID selector?
4. Write the CSS to target all `<p>` elements inside a `<main>` element.
5. What is the difference between `color` and `background-color`?
6. What does `font-family` do, and why do we list multiple fonts?
7. What does `line-height: 1.6` mean?
8. What is the cascade in CSS?
9. Which has higher specificity — a class or an ID?
10. What does `!important` do, and why should you avoid it?

---

## 13. Homework

**Task 1 — Style your registration page** from Lesson 3:

- Give the form a white background with some padding
- Style the input fields — add a border, some padding, and make them full width
- Style the submit button — give it a background color, white text, and a hover effect
- Use your Google Font on the entire page

**Task 2 — Research for next class:**

Look up and be ready to explain:
- What is the CSS Box Model?
- What is the difference between `margin` and `padding`?
- What does `box-sizing: border-box` do?

**Push everything to GitHub before the next session.**

---

## What's Coming Next

| Lesson | Topic |
|--------|-------|
| **Next class** | The CSS Box Model — margin, padding, border |
| Soon | Flexbox — modern layout |
| Later | CSS Grid — advanced layout |
| Then | Bootstrap — building faster |

> You can now style any HTML element. Next class we learn how spacing and layout work — this is where your pages start to look truly professional.

---

*Fadidev Studio — Front-End Web Development Training*
*Lesson 4 | Introduction to CSS*