# 03 - CSS Basics 🎨

## What is CSS?
- **Cascading Style Sheet**
- Used for **styling web pages** — making them beautiful
- Controls **visual appearance** of HTML elements
- It is a **styling language** (not a programming language)

---

## CSS Syntax

```css
selector {
  property: value;
  property: value;
}
```

### Example:
```css
p {
  color: red;
  font-size: 20px;
}
```

| Part | Meaning |
|------|---------|
| `p` | Selector — which element to style |
| `color` | Property — what to change |
| `red` | Value — what to change it to |
| `;` | Semicolon — ends each declaration |
| `{ }` | Curly braces — wraps all the rules |

---

## 3 Ways to Write CSS

### Way 1 — Inline CSS (avoid this)
Write style **directly on the element**:

```html
<p style="color: red; font-size: 20px;">This is red text</p>
```

❌ **Problem** — have to repeat on every element. Gets messy fast.

---

### Way 2 — Internal CSS ✅ (good for learning)
Write inside a `<style>` tag in the `<head>`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>

    <style>
      p {
        color: red;
      }
      h1 {
        color: blue;
      }
    </style>

  </head>
  <body>
    <h1>Blue Heading</h1>
    <p>Red paragraph</p>
  </body>
</html>
```

✅ **Good for** — small pages and when learning

---

### Way 3 — External CSS ✅✅ (best practice)
Create a **separate `.css` file** and link it in `<head>`:

**index.html:**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>My Heading</h1>
    <p>My paragraph</p>
  </body>
</html>
```

**style.css:**
```css
h1 {
  color: blue;
}

p {
  color: red;
  font-size: 18px;
}
```

✅ **Best because:**
- One CSS file can style **100 HTML pages**
- Change one file → everything updates
- Keeps HTML and CSS **separate and clean**

---

## Comparison Table

| | Inline | Internal | External |
|--|--------|----------|----------|
| Where written | On the tag | `<head>` in `<style>` | Separate `.css` file |
| Reusable | ❌ No | ⚠️ Same page only | ✅ Across all pages |
| Best for | Never | Learning / small pages | All real projects |

---

## Common CSS Properties

```css
/* Text */
color: red;                    /* text color */
font-size: 20px;               /* text size */
font-weight: bold;             /* bold text */
font-family: Arial, sans-serif;/* font style */
text-align: center;            /* align text */

/* Background */
background-color: yellow;      /* background color */

/* Box */
width: 200px;                  /* width */
height: 100px;                 /* height */
padding: 10px;                 /* space inside */
margin: 10px;                  /* space outside */
border: 2px solid black;       /* border */
border-radius: 5px;            /* rounded corners */
```

---

## CSS Comments

```css
/* This is a CSS comment — not applied to page */
p {
  color: red; /* this makes text red */
}
```
