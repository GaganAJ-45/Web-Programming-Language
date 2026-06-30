# 06 - Lists & Tables 📋

## Lists

There are 2 types of lists in HTML.

-----

## 1. Unordered List — `<ul>`

Shows items with **bullet points** (no numbering):

```html
<ul>
<li>HTML</li>
<li>CSS</li>
<li>Javascript</li>
</ul>

```

**Output:**
- HTML
- CSS
- JavaScript

---

## 2. Ordered List — `<ol>`

Shows items with **numbers** (1, 2, 3...):

```html
<ol>
  <li>Wake up</li>
  <li>Open VS Code</li>
  <li>Write HTML</li>
</ol>
```

**Output:**
1. Wake up
2. Open VS Code
3. Write HTML

---

## `<li>` — List Item

- `<li>` means **list item**
- Used inside both `<ul>` and `<ol>`
- Every item in a list needs to be inside `<li>`

---

## Nested Lists (List inside a List)

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Node.js</li>
      <li>Python</li>
    </ul>
  </li>
</ul>
```

---

## Styling Lists with CSS

```css
/* Remove bullet points */
ul {
  list-style-type: none;
}

/* Change bullet style */
ul {
  list-style-type: square;   /* square bullets */
  list-style-type: circle;   /* circle bullets */
  list-style-type: disc;     /* default filled circle */
}

/* Change number style */
ol {
  list-style-type: upper-roman;   /* I, II, III */
  list-style-type: lower-alpha;   /* a, b, c */
}
```

---

## Tables

Tables are used to display **data in rows and columns**.

### Basic table tags:

| Tag | Purpose |
|-----|---------|
| `<table>` | Creates the table |
| `<tr>` | Table Row |
| `<th>` | Table Header (bold, centered by default) |
| `<td>` | Table Data (regular cell) |
| `<thead>` | Groups header rows |
| `<tbody>` | Groups body rows |

---

## Basic Table Example

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>
  <tr>
    <td>Aj</td>
    <td>22</td>
    <td>Bengaluru</td>
  </tr>
  <tr>
    <td>Rahul</td>
    <td>25</td>
    <td>Mumbai</td>
  </tr>
</table>
```

---

## Styling Tables with CSS

```html
<style>
  table {
    width: 100%;
    border-collapse: collapse;   /* removes double borders */
  }

  th, td {
    border: 1px solid black;
    padding: 10px;
    text-align: left;
  }

  th {
    background-color: #333;
    color: white;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;  /* alternate row colors */
  }
</style>
```

---

## Full Example — List + Table Together

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Lists and Tables</title>
    <style>
      table { border-collapse: collapse; width: 100%; }
      th, td { border: 1px solid #ccc; padding: 8px; }
      th { background-color: #4CAF50; color: white; }
    </style>
  </head>
  <body>

    <h2>My Subjects</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>

    <h2>My Study Plan</h2>
    <ol>
      <li>Learn HTML basics</li>
      <li>Learn CSS styling</li>
      <li>Build projects</li>
    </ol>

    <h2>Student Table</h2>
    <table>
      <tr>
        <th>Name</th>
        <th>Subject</th>
        <th>Score</th>
      </tr>
      <tr>
        <td>Aj</td>
        <td>HTML</td>
        <td>95</td>
      </tr>
      <tr>
        <td>Rahul</td>
        <td>CSS</td>
        <td>88</td>
      </tr>
    </table>

  </body>
</html>
```
