# 08 - Semantic HTML & Layout 🏛️

## What is Semantic HTML?
- Semantic = **meaningful**
- Semantic tags describe **what the content is**, not just how it looks
- Makes code more readable for developers and browsers

### Non-semantic (bad):
```html
<div>Header content</div>
<div>Navigation links</div>
<div>Main content</div>
<div>Footer</div>
```

### Semantic (good):
```html
<header>Header content</header>
<nav>Navigation links</nav>
<main>Main content</main>
<footer>Footer</footer>
```

Both look the same in the browser — but the second one **makes sense** when you read the code.

---

## Why Semantic HTML Matters
- Makes code **easier to read and understand**
- Helps **search engines** (Google) understand your page better — good for SEO
- Helps **screen readers** for visually impaired users
- Better **team collaboration** — other developers understand your code

---

## Semantic Tags

| Tag | Purpose |
|-----|---------|
| `<header>` | Top section of page or section (logo, title) or introduction part |
| `<nav>` | Navigation links / menu |
| `<main>` | Main content of the page (use only once) |
| `<section>` | A group of related content |
| `<article>` | Self-contained content (blog post, news) |
| `<aside>` | Side content (sidebar, ads, related links) |
| `<footer>` | Bottom of page (copyright, links) or concluded part |
| `<figure>` | Image with caption |
| `<figcaption>` | Caption for a figure |

---

## `<div>` and `<span>`

These are **non-semantic** but still very useful for layout:

### `<div>` — Division
- A **block-level** container
- Used to group elements together
- Takes up the **full width** of the page

```html
<div class="card">
  <h2>Card Title</h2>
  <p>Card content here</p>
</div>
```

### `<span>` — Inline container
- An **inline** container
- Used to style a **small part** of text
- Only takes up as much space as its content

```html
<p>My favourite color is <span class="highlight">blue</span>.</p>
```

---

## Block vs Inline Elements

### Block elements:
- Start on a **new line**
- Take up **full width** available
- Stack on top of each other

```html
<div>, <p>, <h1>-<h6>, <ul>, <ol>, <li>,
<header>, <nav>, <main>, <section>, <footer>
```

### Inline elements:
- Stay on the **same line**
- Only take up as much **width as needed**

```html
<span>, <a>, <strong>, <em>, <img>, <input>, <label>
```

---

## Full Page Layout Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Website</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      body {
        font-family: Arial, sans-serif;
      }
      header {
        background-color: #333;
        color: white;
        padding: 20px;
        text-align: center;
      }
      nav {
        background-color: #444;
        padding: 10px;
        text-align: center;
      }
      nav a {
        color: white;
        margin: 0 15px;
        text-decoration: none;
      }
      main {
        max-width: 800px;
        margin: 20px auto;
        padding: 0 20px;
      }
      section {
        margin-bottom: 30px;
      }
      aside {
        background-color: #f4f4f4;
        padding: 15px;
        border-left: 4px solid #333;
      }
      footer {
        background-color: #333;
        color: white;
        text-align: center;
        padding: 15px;
        margin-top: 30px;
      }
      .highlight {
        color: #4CAF50;
        font-weight: bold;
      }
    </style>
  </head>
  <body>

    <header>
      <h1>My Learning Website</h1>
      <p>HTML & CSS Notes</p>
    </header>

    <nav>
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>

    <main>

      <section id="home">
        <h2>Welcome</h2>
        <p>I am learning <span class="highlight">HTML & CSS</span> from scratch.</p>
      </section>

      <section id="about">
        <h2>About Me</h2>
        <article>
          <h3>My Story</h3>
          <p>I started learning web development in June 2026.</p>
        </article>
      </section>

      <aside>
        <h3>Quick Tip</h3>
        <p>Practice every day — even 30 minutes helps a lot!</p>
      </aside>

    </main>

    <footer>
      <p>© 2026 My Website. All rights reserved.</p>
    </footer>

  </body>
</html>
```

---

## Quick Summary

```
<header>   → top of page
<nav>      → menu / links
<main>     → main content (once per page)
  <section>  → group of content
  <article>  → standalone piece of content
  <aside>    → sidebar / extra info
<footer>   → bottom of page

<div>   → block container (no meaning)
<span>  → inline container (no meaning)
```
