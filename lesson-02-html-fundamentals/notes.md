# Introduction to HTML
### Fadidev Studio — Front-End Web Development Training
**Lesson 2 | The Web & HTML Fundamentals**

---

## What We Cover Today

1. [What Is the Web?](#1-what-is-the-web)
2. [What Is HTML?](#2-what-is-html)
3. [HTML Tags and Elements](#3-html-tags-and-elements)
4. [Attributes](#4-attributes)
5. [The HTML Document Structure](#5-the-html-document-structure)
6. [Core HTML Tags You Must Know](#6-core-html-tags-you-must-know)
7. [Links and Images](#7-links-and-images)
8. [Lists](#8-lists)
9. [Your First Web Page — Practice Task](#9-your-first-web-page--practice-task)
10. [Recap Questions](#10-recap-questions)
11. [Homework](#11-homework)

---

## Quick Recap From Last Class

Before we begin, answer these quickly:

- What is the difference between the internet and the web?
- What does DNS do?
- What is an HTTP status code? Give one example.
- What is the DOM?

---

## 1. What Is the Web?

The **World Wide Web** is a collection of billions of documents (web pages) stored on servers around the world, all connected to each other through **hyperlinks**.

When you open a browser and visit a website:

1. The browser requests files from a server
2. The server sends back files written in **HTML**, **CSS**, and **JavaScript**
3. The browser reads those files and displays the page visually

Every website you have ever used — Google, YouTube, Instagram, any e-commerce store — started as a plain text file written in HTML.

> As a front-end developer, writing HTML is the very first thing you learn. It is the skeleton of every web page.

---

## 2. What Is HTML?

**HTML** stands for **HyperText Markup Language**.

Let us break that down:

| Word | Meaning |
|------|---------|
| **HyperText** | Text that contains links to other documents |
| **Markup** | A system of tags that annotate and structure content |
| **Language** | A defined set of rules for writing those tags |

### Important: HTML Is NOT a Programming Language

HTML does not have logic. It cannot make decisions, run loops, or calculate anything. It is purely a **structure language** — it describes what content is on the page and what type each piece of content is.

- A paragraph? HTML.
- A heading? HTML.
- An image? HTML.
- A clickable button? HTML.

CSS makes it look good. JavaScript makes it interactive. But HTML builds the foundation that everything else sits on.

### What Does HTML Look Like?

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First Page</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <p>This is my first web page.</p>
  </body>
</html>
```

Save that as `index.html`, open it in a browser, and you have a web page.

---

## 3. HTML Tags and Elements

HTML is written using **tags**. A tag is a keyword surrounded by angle brackets.

### Opening and Closing Tags

Most HTML elements have an **opening tag** and a **closing tag**. The closing tag has a forward slash before the keyword.

```html
<tagname>Content goes here</tagname>
```

Examples:

```html
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
<strong>This text is bold.</strong>
```

### The Anatomy of an HTML Element

```
<p>This is a paragraph.</p>
^    ^                  ^
|    |                  |
|    Content            Closing tag
Opening tag
```

The whole thing — opening tag + content + closing tag — is called an **element**.

### Self-Closing Tags

Some tags do not wrap around content. They are self-closing — they stand alone.

```html
<br>       <!-- line break -->
<hr>       <!-- horizontal rule / divider line -->
<img>      <!-- image -->
<input>    <!-- form input field -->
```

> In older HTML (XHTML), you would write these as `<br />` with a slash. In modern HTML5, the slash is optional. Both work.

---

## 4. Attributes

**Attributes** give extra information about an element. They are always written inside the opening tag.

```html
<tagname attribute="value">Content</tagname>
```

Examples:

```html
<!-- An image with a source and alt text -->
<img src="photo.jpg" alt="A photo of a cat">

<!-- A link with a destination -->
<a href="https://google.com">Go to Google</a>

<!-- An input with a type -->
<input type="text">
```

### Rules for Attributes

- Always written in the **opening tag**, never the closing tag
- Written as `name="value"` pairs
- An element can have multiple attributes
- Some attributes are **required** (like `src` on an image), others are optional

```html
<!-- Multiple attributes on one element -->
<a href="https://google.com" target="_blank" title="Opens Google">Click here</a>
```

---

## 5. The HTML Document Structure

Every valid HTML page has the same basic structure. This is the **boilerplate** — the starting template you use every time.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title Here</title>
  </head>
  <body>

    <!-- Your visible content goes here -->

  </body>
</html>
```

### Breaking It Down

**`<!DOCTYPE html>`**
- Not an HTML tag — it is a declaration
- Tells the browser: "This document is written in HTML5"
- Always the very first line of every HTML file
- Without it, browsers go into "quirks mode" and may display things incorrectly

**`<html lang="en">`**
- The root element — everything else goes inside this
- `lang="en"` tells the browser and search engines the language of the page

**`<head>`**
- Contains information **about** the page — not visible content
- Think of it as metadata: the page's title, character encoding, linked CSS files, etc.
- Nothing inside `<head>` appears on the visible page

**`<meta charset="UTF-8">`**
- Tells the browser which character encoding to use
- UTF-8 supports virtually every character and symbol in the world
- Always include this

**`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**
- Makes the page responsive on mobile devices
- Without this, mobile browsers zoom out and show the page as if it were a desktop screen

**`<title>`**
- The text that appears in the browser tab
- Also used by search engines as the page title in search results

**`<body>`**
- Everything the user actually **sees** on the page goes here
- Text, images, links, buttons, forms — all of it lives inside `<body>`

---

## 6. Core HTML Tags You Must Know

### Headings

HTML has six levels of headings, from `<h1>` (largest, most important) to `<h6>` (smallest, least important).

```html
<h1>Main Page Title</h1>
<h2>Section Heading</h2>
<h3>Sub-section Heading</h3>
<h4>Smaller Heading</h4>
<h5>Even Smaller</h5>
<h6>Smallest Heading</h6>
```

> **Rule:** Use only ONE `<h1>` per page. It represents the main topic of the page. Search engines use headings to understand page structure.

### Paragraphs

```html
<p>This is a paragraph of text. It can be as long or as short as needed.</p>
<p>This is a second paragraph. Each p tag creates a new block of text.</p>
```

### Text Formatting

```html
<strong>Bold text</strong>        <!-- important/bold -->
<em>Italic text</em>              <!-- emphasis/italic -->
<u>Underlined text</u>            <!-- underline -->
<mark>Highlighted text</mark>     <!-- highlight -->
<del>Strikethrough text</del>     <!-- deleted/strikethrough -->
<small>Smaller text</small>       <!-- small print -->
```

### Line Break and Divider

```html
<p>Line one.<br>Line two on the same paragraph.</p>

<hr>   <!-- draws a horizontal line across the page -->
```

### Division and Span

```html
<!-- div is a block-level container — takes up full width -->
<div>
  <p>This paragraph is inside a div.</p>
  <p>So is this one.</p>
</div>

<!-- span is an inline container — only wraps around inline content -->
<p>My favourite colour is <span>blue</span>.</p>
```

> `div` and `span` have no visual appearance by default. They become useful when you add CSS to style them.

### Comments

Comments are notes for you — the browser ignores them completely.

```html
<!-- This is a comment. It will not appear on the page. -->
<p>This text is visible.</p>
<!-- TODO: Add a contact form here later -->
```

---

## 7. Links and Images

### Links — The `<a>` Tag

The `<a>` tag (anchor) creates a hyperlink.

```html
<a href="https://google.com">Go to Google</a>
```

**Important attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `href` | The URL or destination | `href="https://google.com"` |
| `target` | Where to open the link | `target="_blank"` (new tab) |
| `title` | Tooltip on hover | `title="Visit Google"` |

```html
<!-- Opens in same tab (default) -->
<a href="https://google.com">Google</a>

<!-- Opens in a new tab -->
<a href="https://google.com" target="_blank">Google (new tab)</a>

<!-- Link to another page in the same project -->
<a href="about.html">About Us</a>

<!-- Link to a section on the same page -->
<a href="#contact">Jump to Contact</a>
```

### Images — The `<img>` Tag

The `<img>` tag embeds an image. It is self-closing and requires two attributes.

```html
<img src="cat.jpg" alt="A photo of a cat">
```

| Attribute | Purpose |
|-----------|---------|
| `src` | The path or URL of the image file |
| `alt` | Alternative text if the image fails to load — also used by screen readers |
| `width` | Width of the image in pixels (optional) |
| `height` | Height of the image in pixels (optional) |

```html
<!-- Image from your project folder -->
<img src="images/profile.jpg" alt="Profile photo" width="200">

<!-- Image from the internet -->
<img src="https://example.com/photo.jpg" alt="Example photo">
```

> **Always include `alt` text.** It helps visually impaired users who use screen readers, and it appears if the image fails to load. It also helps with SEO.

---

## 8. Lists

HTML has three types of lists.

### Unordered List — Bullet Points

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

Renders as:
- HTML
- CSS
- JavaScript

### Ordered List — Numbered

```html
<ol>
  <li>Learn HTML</li>
  <li>Learn CSS</li>
  <li>Learn JavaScript</li>
</ol>
```

Renders as:
1. Learn HTML
2. Learn CSS
3. Learn JavaScript

### Description List — Term and Definition

```html
<dl>
  <dt>HTML</dt>
  <dd>The structure of a web page</dd>

  <dt>CSS</dt>
  <dd>The styling of a web page</dd>

  <dt>JavaScript</dt>
  <dd>The interactivity of a web page</dd>
</dl>
```

### Nested Lists

Lists can go inside lists.

```html
<ul>
  <li>Front-end
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Back-end
    <ul>
      <li>Node.js</li>
      <li>Python</li>
    </ul>
  </li>
</ul>
```

---

## 9. Your First Web Page — Practice Task

Build a simple "About Me" page using everything covered today.

**Requirements:**

Your page must include:

- The correct HTML boilerplate (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`)
- A `<title>` in the head
- An `<h1>` with your name
- An `<h2>` with a subtitle like "Front-End Developer"
- At least two `<p>` tags introducing yourself
- An `<img>` (use any image — a profile photo or a placeholder)
- An unordered list of 3 things you want to learn
- A link to any website you use often
- At least one use of `<strong>` or `<em>` inside a paragraph

**Starter template:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me</title>
  </head>
  <body>

    <h1>Your Name Here</h1>
    <h2>Front-End Developer in Training</h2>

    <img src="" alt="My photo">

    <p>Write something about yourself here...</p>
    <p>Write a second paragraph here...</p>

    <h3>What I Want to Learn</h3>
    <ul>
      <li>Item one</li>
      <li>Item two</li>
      <li>Item three</li>
    </ul>

    <p>Visit my favourite website: <a href="">Click here</a></p>

  </body>
</html>
```

**How to run it:**
1. Open VS Code
2. Create a new file called `index.html`
3. Paste and complete the template
4. Right-click the file → Open with Live Server
5. Your page will open in the browser

---

## 10. Recap Questions

Test your understanding:

1. What does HTML stand for?
2. Is HTML a programming language? Why or why not?
3. What is the difference between an opening tag and a closing tag?
4. What is an attribute? Give an example.
5. What goes inside the `<head>` tag? What goes inside `<body>`?
6. What does `<!DOCTYPE html>` do?
7. What is the difference between `<div>` and `<span>`?
8. Why is `alt` text important on an image?
9. What is the difference between `<ul>` and `<ol>`?
10. How do you open a link in a new tab?

---

## 11. Homework

**Task 1 — Expand your About Me page**

Add the following to what you built in class today:

- A `<h2>` section called "My Skills" with a list of any skills you have (not just coding)
- A `<h2>` section called "Contact" with your email written as a `mailto` link:

```html
<a href="mailto:yourname@email.com">Email me</a>
```

- A horizontal rule `<hr>` between each section
- A footer at the bottom of the page using the `<footer>` tag:

```html
<footer>
  <p>Built by Your Name — 2025</p>
</footer>
```

**Task 2 — Research**

Look up and be ready to explain next class:

- What is a **semantic HTML element**? Give 3 examples.
- What is the difference between `<div>` and `<section>`?
- Why do search engines care about your HTML structure?

**Push your work to GitHub before the next session.**

---

## What's Coming Next

| Lesson | Topic |
|--------|-------|
| Next class | CSS — Styling your HTML page |
| Soon | CSS Box Model, Flexbox, Grid |
| Later | Bootstrap — building faster with a CSS framework |

---

*Fadidev Studio — Front-End Web Development Training*
*Lesson 2 | The Web & HTML Fundamentals*