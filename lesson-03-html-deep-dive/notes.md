# HTML Continued — Forms, Tables & Semantic Elements
### Fadidev Studio — Front-End Web Development Training
**Lesson 3 | HTML Deep Dive**

---

## What We Cover Today

1. [Quick Recap](#1-quick-recap)
2. [Semantic HTML](#2-semantic-html)
3. [Tables](#3-tables)
4. [Forms](#4-forms)
5. [Putting It All Together — Practice Task](#5-putting-it-all-together--practice-task)
6. [Recap Questions](#6-recap-questions)
7. [Homework](#7-homework)

---

## 1. Quick Recap

Before we continue, answer these quickly:

- What is the correct HTML boilerplate structure?
- What is the difference between `<div>` and `<span>`?
- How do you open a link in a new tab?
- What attribute is required on every `<img>` tag and why?
- What is the difference between `<ul>` and `<ol>`?

---

## 2. Semantic HTML

### What Is Semantic HTML?

In the last lesson we used `<div>` a lot. A `<div>` is a generic container — it means nothing on its own. It just wraps content.

**Semantic elements** are HTML tags that carry **meaning**. They tell the browser, the developer, and search engines exactly what role that section of the page plays.

Compare these two:

**Without semantics — hard to read, meaningless structure:**
```html
<div>
  <div>My Website</div>
  <div>
    <div>Home</div>
    <div>About</div>
    <div>Contact</div>
  </div>
</div>

<div>
  <div>
    <h1>Welcome to my page</h1>
    <p>This is the main content.</p>
  </div>
  <div>
    <p>Related links</p>
  </div>
</div>

<div>
  <p>Built by Abdul — 2025</p>
</div>
```

**With semantics — clear, meaningful structure:**
```html
<header>
  <h1>My Website</h1>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </nav>
</header>

<main>
  <article>
    <h2>Welcome to my page</h2>
    <p>This is the main content.</p>
  </article>
  <aside>
    <p>Related links</p>
  </aside>
</main>

<footer>
  <p>Built by Abdul — 2025</p>
</footer>
```

Both render the same way visually. But the second version tells everyone reading the code — and every search engine crawling it — exactly what each section is for.

### Why Semantics Matter

- **Readability** — Other developers (and future you) can understand the page structure instantly
- **SEO** — Search engines like Google rank pages higher when they use proper semantic structure
- **Accessibility** — Screen readers used by visually impaired users rely on semantic elements to navigate pages
- **Maintainability** — Easier to style with CSS and update later

### The Core Semantic Elements

#### Page Layout Elements

```html
<header>
  <!-- Top of the page or a section -->
  <!-- Usually contains the logo, site title, and navigation -->
</header>

<nav>
  <!-- Navigation links -->
  <!-- Use this for your main menu, sidebar links, etc. -->
</nav>

<main>
  <!-- The primary content of the page -->
  <!-- Only ONE <main> per page -->
</main>

<footer>
  <!-- Bottom of the page or a section -->
  <!-- Usually contains copyright, contact links, social media -->
</footer>

<aside>
  <!-- Secondary content alongside the main content -->
  <!-- Sidebar, related articles, ads, extra info -->
</aside>
```

#### Content Elements

```html
<section>
  <!-- A thematic grouping of content -->
  <!-- Like chapters in a book — each section is a distinct topic -->
  <!-- Always has a heading inside it -->
</section>

<article>
  <!-- A self-contained, independently meaningful piece of content -->
  <!-- Blog post, news article, product card, forum post -->
  <!-- Could be lifted out of the page and still make sense on its own -->
</article>

<h1> to <h6>
  <!-- Already covered — but these are semantic too -->
  <!-- They tell the browser the hierarchy of your content -->
```

#### Inline Semantic Elements

```html
<strong>Important text</strong>     <!-- Important, serious — bold by default -->
<em>Emphasised text</em>            <!-- Emphasis — italic by default -->
<mark>Highlighted text</mark>       <!-- Relevant/highlighted -->
<time datetime="2025-01-01">New Year's Day</time>   <!-- A date or time -->
<abbr title="HyperText Markup Language">HTML</abbr> <!-- An abbreviation -->
<cite>The Great Gatsby</cite>       <!-- A title of a work -->
<code>console.log()</code>         <!-- A piece of code inline -->
```

### Section vs Article vs Div — When to Use Which

| Element | Use when... |
|---------|------------|
| `<div>` | No semantic meaning needed — purely for layout/styling |
| `<section>` | A distinct themed group of content with a heading |
| `<article>` | Standalone content that makes sense on its own |
| `<aside>` | Content related but secondary to the main content |

### A Full Semantic Page Layout

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog</title>
  </head>
  <body>

    <header>
      <h1>Abdul's Blog</h1>
      <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="contact.html">Contact</a>
      </nav>
    </header>

    <main>

      <section>
        <h2>Latest Posts</h2>

        <article>
          <h3>How the Internet Works</h3>
          <p>Published on <time datetime="2025-04-18">April 18, 2025</time></p>
          <p>A complete guide for beginner web developers...</p>
          <a href="post.html">Read more</a>
        </article>

        <article>
          <h3>Introduction to HTML</h3>
          <p>Published on <time datetime="2025-04-20">April 20, 2025</time></p>
          <p>Everything you need to know to get started...</p>
          <a href="post.html">Read more</a>
        </article>

      </section>

      <aside>
        <h3>About the Author</h3>
        <p>Abdul is a front-end developer and educator at Fadidev Studio.</p>
      </aside>

    </main>

    <footer>
      <p>&copy; 2025 Abdul — Fadidev Studio. All rights reserved.</p>
    </footer>

  </body>
</html>
```

---

## 3. Tables

### What Are Tables For?

HTML tables are used to display **tabular data** — information that naturally fits in rows and columns, like a spreadsheet.

> **Important:** Tables are for data, not for page layout. In the early days of the web, developers used tables to arrange the entire page layout. This is outdated and wrong. Use CSS for layout. Use tables only for actual data.

Examples of good table use:
- A class timetable
- A price comparison chart
- A list of students and their grades
- Sports league standings

### Basic Table Structure

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>
  <tr>
    <td>Abdul</td>
    <td>25</td>
    <td>Douala</td>
  </tr>
  <tr>
    <td>Aisha</td>
    <td>22</td>
    <td>Yaounde</td>
  </tr>
</table>
```

### Table Tags Explained

| Tag | What It Does |
|-----|-------------|
| `<table>` | The container for the entire table |
| `<tr>` | Table Row — creates a row |
| `<th>` | Table Header — a heading cell (bold and centred by default) |
| `<td>` | Table Data — a regular data cell |
| `<thead>` | Groups the header rows |
| `<tbody>` | Groups the body rows |
| `<tfoot>` | Groups the footer rows |
| `<caption>` | A title/description for the table |

### A Well-Structured Table

Always use `<thead>`, `<tbody>`, and optionally `<tfoot>` to organise your table properly. This is important for accessibility and for applying CSS styles.

```html
<table>
  <caption>Student Scores — April 2025</caption>

  <thead>
    <tr>
      <th>Student</th>
      <th>HTML</th>
      <th>CSS</th>
      <th>JavaScript</th>
      <th>Total</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Aisha</td>
      <td>85</td>
      <td>90</td>
      <td>78</td>
      <td>253</td>
    </tr>
    <tr>
      <td>Kwame</td>
      <td>92</td>
      <td>88</td>
      <td>95</td>
      <td>275</td>
    </tr>
    <tr>
      <td>Fatima</td>
      <td>76</td>
      <td>82</td>
      <td>80</td>
      <td>238</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Class Average</td>
      <td>84</td>
      <td>87</td>
      <td>84</td>
      <td>255</td>
    </tr>
  </tfoot>

</table>
```

### Spanning Columns and Rows

Sometimes a cell needs to stretch across multiple columns or rows.

**`colspan`** — merges cells horizontally (across columns):

```html
<table>
  <tr>
    <th colspan="3">Student Results</th>   <!-- spans 3 columns -->
  </tr>
  <tr>
    <th>Name</th>
    <th>Score</th>
    <th>Grade</th>
  </tr>
  <tr>
    <td>Aisha</td>
    <td>85</td>
    <td>A</td>
  </tr>
</table>
```

**`rowspan`** — merges cells vertically (across rows):

```html
<table>
  <tr>
    <td rowspan="2">Monday</td>   <!-- spans 2 rows -->
    <td>HTML</td>
  </tr>
  <tr>
    <td>CSS</td>
  </tr>
</table>
```

---

## 4. Forms

### What Are Forms For?

Forms are how users send data to a web page or server. Every time you:

- Log in to a website
- Sign up for an account
- Search on Google
- Fill in a contact form
- Place an order online

...you are using an HTML form.

### The `<form>` Element

The `<form>` tag wraps all the input fields and controls.

```html
<form action="/submit" method="POST">
  <!-- form fields go here -->
</form>
```

| Attribute | What It Does |
|-----------|-------------|
| `action` | The URL where the form data is sent when submitted |
| `method` | How the data is sent — `GET` or `POST` |

- **GET** — data is added to the URL (used for searches, filters)
- **POST** — data is sent in the request body, not visible in the URL (used for login, registration, sensitive data)

### The `<input>` Element

`<input>` is the most used form element. It creates different types of fields depending on the `type` attribute.

```html
<!-- Text field -->
<input type="text" name="username" placeholder="Enter your name">

<!-- Password field — hides characters -->
<input type="password" name="password" placeholder="Enter password">

<!-- Email field — validates email format -->
<input type="email" name="email" placeholder="your@email.com">

<!-- Number field -->
<input type="number" name="age" min="1" max="100">

<!-- Phone number -->
<input type="tel" name="phone" placeholder="+237 6XX XXX XXX">

<!-- Date picker -->
<input type="date" name="dob">

<!-- File upload -->
<input type="file" name="photo">

<!-- Checkbox -->
<input type="checkbox" name="agree" value="yes"> I agree to the terms

<!-- Radio buttons — only one can be selected at a time -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female

<!-- Hidden field — not visible to user -->
<input type="hidden" name="user_id" value="123">

<!-- Submit button -->
<input type="submit" value="Submit Form">
```

### The `<label>` Element

Every input should have a `<label>`. It tells the user what the field is for and improves accessibility.

**Method 1 — using `for` and `id`:**
```html
<label for="username">Full Name</label>
<input type="text" id="username" name="username">
```

The `for` attribute on the label must match the `id` on the input. When the user clicks the label, the input gets focused — a better user experience.

**Method 2 — wrapping the input inside the label:**
```html
<label>
  Full Name
  <input type="text" name="username">
</label>
```

### Other Form Elements

**`<textarea>` — multi-line text input:**
```html
<label for="message">Your Message</label>
<textarea id="message" name="message" rows="5" cols="40" placeholder="Write your message here..."></textarea>
```

**`<select>` — dropdown menu:**
```html
<label for="country">Country</label>
<select id="country" name="country">
  <option value="">-- Select a country --</option>
  <option value="cm">Cameroon</option>
  <option value="ng">Nigeria</option>
  <option value="gh">Ghana</option>
  <option value="sn">Senegal</option>
</select>
```

**`<button>` — a clickable button:**
```html
<!-- Submit button (submits the form) -->
<button type="submit">Send Message</button>

<!-- Reset button (clears all fields) -->
<button type="reset">Clear Form</button>

<!-- Regular button (does nothing by default — used with JavaScript) -->
<button type="button">Click Me</button>
```

### Form Input Attributes

| Attribute | What It Does | Example |
|-----------|-------------|---------|
| `name` | The field name sent with the data | `name="email"` |
| `id` | Unique identifier — links to `<label>` | `id="email"` |
| `placeholder` | Grey hint text inside the field | `placeholder="Enter email"` |
| `value` | Pre-filled value | `value="default text"` |
| `required` | Field must be filled before submitting | `required` |
| `disabled` | Field cannot be edited | `disabled` |
| `readonly` | Field is visible but not editable | `readonly` |
| `min` / `max` | Min and max values for number/date | `min="1" max="100"` |
| `maxlength` | Maximum number of characters | `maxlength="50"` |
| `autofocus` | Automatically focuses this field on page load | `autofocus` |

### Grouping Form Fields with `<fieldset>`

Use `<fieldset>` and `<legend>` to group related fields together.

```html
<form action="/register" method="POST">

  <fieldset>
    <legend>Personal Information</legend>

    <label for="fname">First Name</label>
    <input type="text" id="fname" name="fname" required>

    <label for="lname">Last Name</label>
    <input type="text" id="lname" name="lname" required>

    <label for="dob">Date of Birth</label>
    <input type="date" id="dob" name="dob">
  </fieldset>

  <fieldset>
    <legend>Account Details</legend>

    <label for="email">Email Address</label>
    <input type="email" id="email" name="email" required>

    <label for="password">Password</label>
    <input type="password" id="password" name="password" required minlength="8">
  </fieldset>

  <button type="submit">Create Account</button>

</form>
```

### A Complete Contact Form

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Us</title>
  </head>
  <body>

    <header>
      <h1>Fadidev Studio</h1>
      <nav>
        <a href="index.html">Home</a>
        <a href="contact.html">Contact</a>
      </nav>
    </header>

    <main>
      <section>
        <h2>Get In Touch</h2>
        <p>Fill in the form below and we will get back to you.</p>

        <form action="/contact" method="POST">

          <label for="fullname">Full Name</label>
          <input type="text" id="fullname" name="fullname" placeholder="Your full name" required>

          <label for="email">Email Address</label>
          <input type="email" id="email" name="email" placeholder="your@email.com" required>

          <label for="subject">Subject</label>
          <select id="subject" name="subject">
            <option value="">-- Choose a subject --</option>
            <option value="general">General Enquiry</option>
            <option value="training">Training & Mentorship</option>
            <option value="project">Project Collaboration</option>
          </select>

          <label for="message">Message</label>
          <textarea id="message" name="message" rows="6" placeholder="Write your message here..." required></textarea>

          <label>
            <input type="checkbox" name="newsletter" value="yes">
            Subscribe to newsletter
          </label>

          <button type="submit">Send Message</button>

        </form>
      </section>
    </main>

    <footer>
      <p>&copy; 2025 Fadidev Studio. All rights reserved.</p>
    </footer>

  </body>
</html>
```

---

## 5. Putting It All Together — Practice Task

Build a **Student Registration Page** for Fadidev Studio.

**The page must include:**

**Semantic structure:**
- `<header>` with the studio name and a `<nav>`
- `<main>` wrapping all the content
- `<section>` for the registration form
- `<footer>` at the bottom

**A table** showing the training schedule:

| Day | Time | Topic |
|-----|------|-------|
| Monday | 9:00 AM | HTML |
| Wednesday | 9:00 AM | CSS |
| Friday | 9:00 AM | JavaScript |

**A registration form** with:
- Full name (text, required)
- Email address (email, required)
- Phone number (tel)
- Date of birth (date)
- Gender (radio buttons — Male / Female)
- Course selection (select dropdown — HTML, CSS, JavaScript, React)
- A short message / motivation (textarea)
- A checkbox: "I agree to the training terms"
- A Submit button

**Push to GitHub when done.**

---

## 6. Recap Questions

1. What is the difference between a `<div>` and a `<section>`?
2. When should you use `<article>` instead of `<section>`?
3. Name four semantic layout elements and what each one is used for.
4. What is the difference between `<th>` and `<td>`?
5. What do `colspan` and `rowspan` do?
6. What is the difference between the `GET` and `POST` methods on a form?
7. Why is `<label>` important for form inputs?
8. What does the `required` attribute do on an input?
9. What is the difference between `<input type="submit">` and `<button type="submit">`?
10. What is `<fieldset>` used for?

---

## 7. Homework

**Task 1 — Complete the practice task** if not finished in class.

**Task 2 — Add a "Courses" section to your About Me page** using a table:

Create a table with at least 4 rows showing courses you have taken or plan to take:

| Course | Status | Duration |
|--------|--------|----------|
| HTML | Completed | 2 weeks |
| CSS | In progress | 3 weeks |
| JavaScript | Upcoming | 4 weeks |
| React | Upcoming | 4 weeks |

**Task 3 — Research for next class:**

Look up and be ready to explain:
- What is CSS and what problem does it solve?
- What is the difference between a CSS class and an ID?
- What does "cascading" mean in CSS?

**Push everything to GitHub before the next session.**

---

## What's Coming Next

| Lesson | Topic |
|--------|-------|
| **Next class** | Introduction to CSS — selectors, properties, the box model |
| Soon | Flexbox and Grid layout |
| Later | Bootstrap — building faster with a CSS framework |

> You now know enough HTML to structure any web page. Next class we add CSS and your pages will start to actually look like real websites.

---

*Fadidev Studio — Front-End Web Development Training*
*Lesson 3 | HTML Deep Dive — Forms, Tables & Semantic Elements*