# 02 - HTML Basics 🏗️

## What is HTML?
- **HyperText Markup Language**
- It is **not** a programming language — it is a **markup language**
- Used for building the **structure and blocks** of webpages
- HTML is **not case sensitive** — `<P>` and `<p>` both work
  - But always write in **lowercase** (modern standard)

---

## index.html
- `index.html` represents the **homepage** of a website
- When someone visits your website, the browser loads `index.html` first
- Always name your main file `index.html`

---

## DOCTYPE Declaration

```html
<!DOCTYPE html>
```

- This line tells the browser **"this is an HTML document"**
- Represents the **document type**
- We are currently using **HTML5**
- Must be the **very first line** of every HTML file

---

## Basic HTML Structure

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Page Title</title>
  </head>

  <body>
    <!-- All visible content goes here -->
  </body>

</html>
```

### What each tag does:

| Tag | Purpose |
|-----|---------|
| `<html>` | Root element — wraps everything |
| `<head>` | Info **about** the page (not visible) |
| `<title>` | Text shown on the **browser tab** |
| `<body>` | Everything the **user sees** on the page |

---

## Opening & Closing Tags

Most HTML tags have an **opening** and a **closing** tag:

```html
<h1>Hello World</h1>
 |                |
opening tag    closing tag
               (has a / slash)
```

---

## Headings

There are 6 levels of headings — `<h1>` is the biggest, `<h6>` is the smallest:

```html
<h1>Heading 1 - Biggest</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6 - Smallest</h6>
```

> Use only **one `<h1>`** per page — it's the main title

---

## Paragraph & Text Tags

```html
<p>This is a paragraph</p>

<strong>This is bold text</strong>

<em>This is italic text</em>

<br>   <!-- Line break — no closing tag needed -->

<hr>   <!-- Horizontal line — no closing tag needed -->
```

---

## HTML Comments

Comments are **not shown** on the webpage — only in the code:

```html
<!-- This is a comment -->
<!-- Use comments to explain your code -->
```

---

## Full Example — First Webpage

```html
<!DOCTYPE html>
<html>

  <head>
    <title>My First Page</title>
  </head>

  <body>

    <h1>Hello, I am learning HTML!</h1>

    <p>My name is Aj. I am learning web development.</p>

    <p>I am studying <strong>HTML basics</strong> right now.</p>

    <hr>

    <h2>My Goals</h2>
    <p>I want to become a <em>fullstack developer</em>.</p>

  </body>

</html>
```

---

## Quick Tips
- Always **indent** your code (press Tab) — makes it readable
- In VS Code, type `!` and press **Tab** — full skeleton is auto-generated
- Save file as `.html` extension
- Use **Live Server** extension to see changes instantly in browser

---

## VS Code Shortcut — HTML Boilerplate

Type `!` and press **Enter** (or Tab) in VS Code inside a `.html` file:

```
! → Enter
```

This instantly gives you the full HTML boilerplate (basic template):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

> This is called the **HTML boilerplate** — the starting point for every page.

---

## Character Sets

- Computers don't understand characters — they only understand **binary digits (0s and 1s)**
- A **character set** maps characters to numbers so computers can store them

### ASCII (American Standard Code for Information Interchange)
- **First character set** introduced
- Only for the **English language**
- Example mappings:
  - A = 65
  - B = 66
  - C = 67

### UTF-8 (Unicode Transformation Format)
- Introduced **later** to support **all languages in the world**
- Supports emojis, Arabic, Hindi, Chinese, etc.
- **UTF-8 is the standard** used on the modern web

```html
<!-- Always declare charset in your HTML head -->
<meta charset="UTF-8">
```

---

## Meta Elements

Meta elements go inside `<head>` and give **information about the webpage** to the browser and search engines. They are **not visible** on the page but are used by browsers and SEO.

> Meta = data about data (information about information)

```html
<head>

  <!-- Character set — always first -->
  <meta charset="UTF-8">

  <!-- Viewport — makes page responsive on mobile -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- Keywords — tells Google what your page is about -->
  <meta name="keywords" content="HTML, CSS, web development">

  <!-- Description — shown on Google search results -->
  <meta name="description" content="Learn HTML and CSS from scratch">

</head>
```

| Meta tag | Purpose |
|----------|---------|
| `charset="UTF-8"` | Tells browser which character set to use |
| `name="viewport"` | Makes page look good on mobile |
| `name="keywords"` | SEO — keywords for search engines |
| `name="description"` | SEO — description shown on Google |

---

## HTML Entities — Special Characters

Some characters like `<` and `>` are used by HTML itself, so if you type them in your content, the browser gets confused.

**Problem:**
```html
<p><HTML></p>   <!-- browser thinks <HTML> is a tag! -->
```

**Solution — use HTML entities:**
```html
<p>&lt;HTML&gt;</p>   <!-- displays as: <HTML> -->
```

### Common entities:

| What you want | Entity code | Displays as |
|---------------|-------------|-------------|
| Less than `<` | `&lt;` | < |
| Greater than `>` | `&gt;` | > |
| Ampersand `&` | `&amp;` | & |
| Non-breaking space | `&nbsp;` | (space) |
| Copyright `©` | `&copy;` | © |
| Registered `®` | `&reg;` | ® |
| Em dash `—` | `&mdash;` | — |

### Syntax pattern:
```
&(entity name);
 |              |
 starts        always ends
 with &        with semicolon ;
```

### Example:
```html
<p>Use &lt;p&gt; tag to define paragraphs in HTML</p>
<!-- Shows: Use <p> tag to define paragraphs in HTML -->

<p>Copyright &copy; 2026 My Website</p>
<!-- Shows: Copyright © 2026 My Website -->
```
