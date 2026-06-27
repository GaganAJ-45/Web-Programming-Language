# 04 - CSS Selectors 🎯

## What is a Selector?
A selector tells CSS **which HTML element to style**.

There are 3 main types:

---

## 1. Tag Selector

Targets **every** element of that tag type on the page.

```css
p {
  color: red;
}
```

```html
<p>I am red</p>      <!-- styled ✅ -->
<p>I am red too</p>  <!-- styled ✅ -->
<p>Me too!</p>       <!-- styled ✅ -->
```

- No special symbol needed in CSS
- Styles **ALL** elements of that type
- Cannot target individual elements

---

## 2. Class Selector

Targets elements with a **specific class name**. Uses `.` dot in CSS.

```css
.highlight {
  color: blue;
  font-size: 25px;
}
```

```html
<p>I am normal</p>                      <!-- not styled -->
<p class="highlight">I am blue</p>      <!-- styled ✅ -->
<p class="highlight">I am blue too</p>  <!-- styled ✅ -->
<h1 class="highlight">Also blue</h1>    <!-- styled ✅ -->
```

### Key rules for class:
- Same class can be used on **multiple elements** ✅
- Works on **any tag** (p, h1, div, span...) ✅
- One element can have **multiple classes** ✅

```html
<!-- Multiple classes — separate with a space -->
<p class="big red bold">I have 3 classes</p>
```

```css
.big  { font-size: 30px; }
.red  { color: red; }
.bold { font-weight: bold; }
```

---

## 3. ID Selector

Targets **one single unique element**. Uses `#` hash in CSS.

```css
#main-title {
  color: green;
  font-size: 40px;
}
```

```html
<p>Normal paragraph</p>
<p id="main-title">I am unique and green</p>  <!-- styled ✅ -->
<p>Normal paragraph</p>
```

### Key rules for ID:
- Must be **unique** — only use once per page ✅
- Never repeat the same ID on multiple elements ❌
- Think of it like an **Aadhar card** — one per person

---

## All 3 Together — Full Example

```html
<!DOCTYPE html>
<html>
  <head>
    <style>

      /* Tag selector — styles ALL h1 tags */
      h1 {
        font-family: Arial;
      }

      /* Class selector — styles elements with class="highlight" */
      .highlight {
        background-color: yellow;
      }

      /* ID selector — styles ONE element with id="main-heading" */
      #main-heading {
        color: red;
        font-size: 50px;
      }

    </style>
  </head>
  <body>

    <h1 id="main-heading" class="highlight">
      Red text + Yellow background
    </h1>

    <h1 class="highlight">
      Only Yellow background
    </h1>

    <h1>
      Only Arial font
    </h1>

  </body>
</html>
```

---

## Comparison Table

| | Tag | Class | ID |
|--|-----|-------|----|
| CSS symbol | nothing | `.` dot | `#` hash |
| HTML attribute | just the tag | `class="name"` | `id="name"` |
| Targets | ALL of that tag | Any element with that class | ONE unique element |
| Reusable | Yes | Yes ✅ | No ❌ |
| Multiple per page | Yes | Yes | Only ONE |

---

## Easy Way to Remember

> 🏫 **Tag** = School uniform — everyone wears the same
>
> 🏷️ **Class** = Name tag — a group of people share it
>
> 🪪 **ID** = Aadhar card — unique to ONE person only

---

## When to use which?

| Situation | Use |
|-----------|-----|
| Style ALL paragraphs the same way | Tag selector |
| Style a group of elements | Class selector |
| Style one specific unique element | ID selector |
| In real projects (most of the time) | Class selector |
