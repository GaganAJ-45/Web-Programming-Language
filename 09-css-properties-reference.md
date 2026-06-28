# 09 - CSS Properties Reference 📖

> A complete reference of CSS properties organized by category.
> Use this as a cheat sheet while coding.

---

## How to read this file

```css
selector {
  property: value;   /* what it does */
}
```

---

## 1. TEXT & FONT PROPERTIES

```css
p {
  /* Color */
  color: red;                        /* named color */
  color: #FF0000;                    /* hex color */
  color: rgb(255, 0, 0);            /* RGB color */

  /* Size */
  font-size: 16px;                   /* pixels */
  font-size: 1rem;                   /* relative to root (16px usually) */
  font-size: 1.2em;                  /* relative to parent */

  /* Weight (boldness) */
  font-weight: normal;               /* default */
  font-weight: bold;                 /* bold */
  font-weight: 100;                  /* thin */
  font-weight: 700;                  /* same as bold */

  /* Style */
  font-style: normal;                /* default */
  font-style: italic;                /* italic */

  /* Family (typeface) */
  font-family: Arial, sans-serif;
  font-family: 'Times New Roman', serif;
  font-family: 'Courier New', monospace;

  /* Alignment */
  text-align: left;                  /* default */
  text-align: center;
  text-align: right;
  text-align: justify;

  /* Decoration */
  text-decoration: none;             /* removes underline from links */
  text-decoration: underline;
  text-decoration: line-through;     /* strikethrough */

  /* Transform */
  text-transform: uppercase;         /* ALL CAPS */
  text-transform: lowercase;         /* all small */
  text-transform: capitalize;        /* First Letter Caps */

  /* Spacing */
  letter-spacing: 2px;               /* space between letters */
  word-spacing: 5px;                 /* space between words */
  line-height: 1.5;                  /* space between lines */
}
```

---

## 2. BACKGROUND PROPERTIES

```css
div {
  /* Color */
  background-color: yellow;
  background-color: #f4f4f4;
  background-color: rgba(0, 0, 0, 0.5);  /* with opacity */
  background-color: transparent;

  /* Image */
  background-image: url('bg.jpg');

  /* Repeat */
  background-repeat: no-repeat;     /* don't tile the image */
  background-repeat: repeat;        /* tile both directions */
  background-repeat: repeat-x;      /* tile horizontally only */
  background-repeat: repeat-y;      /* tile vertically only */

  /* Position */
  background-position: center;
  background-position: top left;
  background-position: 50% 50%;

  /* Size */
  background-size: cover;           /* covers entire element */
  background-size: contain;         /* fits inside element */
  background-size: 300px 200px;     /* exact size */

  /* Shorthand — all in one line */
  background: #333 url('bg.jpg') no-repeat center/cover;
}
```

---

## 3. BOX MODEL PROPERTIES

Every HTML element is a box with: content → padding → border → margin

```
┌──────────────────────────────┐
│           MARGIN             │
│   ┌──────────────────────┐   │
│   │        BORDER        │   │
│   │   ┌──────────────┐   │   │
│   │   │   PADDING    │   │   │
│   │   │  ┌────────┐  │   │   │
│   │   │  │CONTENT │  │   │   │
│   │   │  └────────┘  │   │   │
│   │   └──────────────┘   │   │
│   └──────────────────────┘   │
└──────────────────────────────┘
```

```css
div {
  /* Width & Height */
  width: 300px;
  height: 200px;
  max-width: 600px;                  /* won't go bigger than this */
  min-width: 200px;                  /* won't go smaller than this */
  max-height: 400px;
  min-height: 100px;

  /* Padding — space INSIDE the border */
  padding: 20px;                     /* all sides */
  padding: 10px 20px;                /* top/bottom  left/right */
  padding: 10px 20px 30px 40px;     /* top right bottom left (clockwise) */
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 10px;
  padding-left: 20px;

  /* Margin — space OUTSIDE the border */
  margin: 20px;                      /* all sides */
  margin: 10px 20px;
  margin: 0 auto;                    /* centers a block element horizontally */
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;

  /* Border */
  border: 2px solid black;           /* shorthand: width style color */
  border-width: 2px;
  border-style: solid;               /* solid, dashed, dotted, none */
  border-color: red;
  border-top: 3px solid blue;        /* only top border */
  border-radius: 8px;                /* rounded corners */
  border-radius: 50%;                /* makes it a circle */

  /* Box sizing — makes width include padding & border */
  box-sizing: border-box;            /* recommended — always use this */
}
```

---

## 4. DISPLAY & VISIBILITY

```css
div {
  /* Display */
  display: block;                    /* takes full width, new line */
  display: inline;                   /* sits inline, no width/height control */
  display: inline-block;             /* inline but can set width/height */
  display: none;                     /* hides element completely (no space) */
  display: flex;                     /* flexbox layout */
  display: grid;                     /* grid layout */

  /* Visibility */
  visibility: visible;               /* default */
  visibility: hidden;                /* hides but still takes up space */

  /* Opacity */
  opacity: 1;                        /* fully visible */
  opacity: 0.5;                      /* 50% transparent */
  opacity: 0;                        /* invisible (but still takes space) */
}
```

---

## 5. POSITIONING

```css
div {
  position: static;                  /* default — normal flow */
  position: relative;                /* offset from its normal position */
  position: absolute;                /* removed from flow, positioned to nearest parent */
  position: fixed;                   /* stays fixed while scrolling */
  position: sticky;                  /* sticks when you scroll past it */

  /* Used with position (not static) */
  top: 10px;
  right: 20px;
  bottom: 10px;
  left: 20px;

  /* Z-index — which element is on top */
  z-index: 1;                        /* higher number = on top */
  z-index: 999;                      /* very on top (e.g. navbar) */
}
```

---

## 6. FLEXBOX (for layout)

```css
/* Applied to the PARENT container */
.container {
  display: flex;

  /* Direction */
  flex-direction: row;               /* left to right (default) */
  flex-direction: column;            /* top to bottom */
  flex-direction: row-reverse;
  flex-direction: column-reverse;

  /* Horizontal alignment */
  justify-content: flex-start;       /* default, left */
  justify-content: flex-end;         /* right */
  justify-content: center;           /* center */
  justify-content: space-between;    /* equal space between items */
  justify-content: space-around;     /* equal space around items */
  justify-content: space-evenly;     /* equal space everywhere */

  /* Vertical alignment */
  align-items: stretch;              /* default */
  align-items: center;               /* center vertically */
  align-items: flex-start;           /* top */
  align-items: flex-end;             /* bottom */

  /* Wrap */
  flex-wrap: nowrap;                 /* default — all in one line */
  flex-wrap: wrap;                   /* wraps to next line */

  /* Gap between items */
  gap: 10px;                         /* space between flex items */
  gap: 10px 20px;                    /* row-gap column-gap */
}

/* Applied to CHILD items */
.item {
  flex: 1;                           /* takes equal share of space */
  flex: 2;                           /* takes double share */
  align-self: center;                /* overrides parent align-items for this item */
  order: 1;                          /* controls order of item */
}
```

---

## 7. IMAGE PROPERTIES

```css
img {
  width: 300px;
  height: 200px;
  object-fit: cover;                 /* fills box, crops if needed */
  object-fit: contain;               /* fits inside, may show gaps */
  object-fit: fill;                  /* stretches — avoid */
  border-radius: 50%;                /* circle image */
  border: 3px solid #ccc;
  box-shadow: 2px 2px 10px rgba(0,0,0,0.3);
}
```

---

## 8. LINK & BUTTON PROPERTIES

```css
a {
  color: blue;
  text-decoration: none;             /* removes underline */
  cursor: pointer;                   /* hand cursor on hover */
}

/* Pseudo-classes for links */
a:hover  { color: darkblue; }        /* when mouse is over it */
a:active { color: red; }             /* when being clicked */
a:visited { color: purple; }         /* after clicking */

button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;                      /* removes default border */
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #45a049;        /* slightly darker on hover */
}
```

---

## 9. FORM ELEMENT PROPERTIES

```css
input, textarea, select {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  outline: none;                     /* removes default blue outline */
  box-sizing: border-box;
}

input:focus {
  border-color: #4CAF50;             /* highlight when typing */
  box-shadow: 0 0 5px rgba(76,175,80,0.5);
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}
```

---

## 10. LIST PROPERTIES

```css
ul, ol {
  list-style-type: none;             /* removes bullets/numbers */
  list-style-type: disc;             /* filled circle (default ul) */
  list-style-type: circle;           /* empty circle */
  list-style-type: square;           /* square */
  list-style-type: decimal;          /* numbers (default ol) */
  list-style-type: upper-roman;      /* I II III */
  list-style-type: lower-alpha;      /* a b c */

  padding: 0;                        /* remove default padding */
  margin: 0;                         /* remove default margin */
}

li {
  padding: 8px 0;
  border-bottom: 1px solid #eee;    /* separator between items */
}
```

---

## 11. TABLE PROPERTIES

```css
table {
  width: 100%;
  border-collapse: collapse;         /* merges double borders into one */
  border-spacing: 0;
}

th, td {
  border: 1px solid #ddd;
  padding: 12px 15px;
  text-align: left;
}

th {
  background-color: #333;
  color: white;
  font-weight: bold;
}

tr:nth-child(even) {
  background-color: #f2f2f2;        /* stripe alternate rows */
}

tr:hover {
  background-color: #e8f4fd;        /* highlight on hover */
}
```

---

## 12. SHADOW & EFFECTS

```css
div {
  /* Box shadow */
  box-shadow: 2px 2px 10px rgba(0,0,0,0.3);
  /*          x    y   blur    color+opacity */

  /* Multiple shadows */
  box-shadow: 0 2px 4px rgba(0,0,0,0.1), 0 8px 16px rgba(0,0,0,0.1);

  /* Text shadow */
  text-shadow: 1px 1px 3px rgba(0,0,0,0.5);

  /* Transition — smooth animation between states */
  transition: all 0.3s ease;
  transition: background-color 0.2s ease, transform 0.2s ease;

  /* Transform */
  transform: scale(1.05);            /* slightly bigger */
  transform: rotate(45deg);          /* rotate */
  transform: translateX(10px);       /* move right */
  transform: translateY(-10px);      /* move up */
}
```

---

## 13. OVERFLOW

```css
div {
  overflow: visible;                 /* default — content spills out */
  overflow: hidden;                  /* clips content that overflows */
  overflow: scroll;                  /* always shows scrollbar */
  overflow: auto;                    /* scrollbar only when needed */

  overflow-x: hidden;               /* hide horizontal overflow only */
  overflow-y: scroll;               /* scroll vertically only */
}
```

---

## 14. CURSOR

```css
div {
  cursor: default;                   /* normal arrow */
  cursor: pointer;                   /* hand — for clickable things */
  cursor: text;                      /* text input cursor */
  cursor: move;                      /* move icon */
  cursor: not-allowed;               /* disabled icon */
  cursor: wait;                      /* loading spinner */
  cursor: crosshair;
}
```

---

## Quick Reference Card

| Property | Common values |
|----------|--------------|
| `color` | red, #FF0000, rgb(255,0,0) |
| `font-size` | 16px, 1rem, 1.2em |
| `font-weight` | normal, bold, 100–900 |
| `text-align` | left, center, right |
| `background-color` | any color value |
| `width / height` | px, %, auto |
| `padding / margin` | px (1–4 values) |
| `border` | 2px solid black |
| `border-radius` | px or 50% for circle |
| `display` | block, inline, flex, none |
| `position` | static, relative, absolute, fixed |
| `object-fit` | cover, contain, fill |
| `opacity` | 0 to 1 |
| `cursor` | pointer, default, not-allowed |
| `transition` | property duration easing |
| `box-shadow` | x y blur color |
