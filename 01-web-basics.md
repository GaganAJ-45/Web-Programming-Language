# 01 - Web Basics 🌐

## Every web development has two parts
1. **Frontend** - what the user sees (HTML, CSS, JavaScript)
2. **Backend** - the server side (databases, logic)
3. **Fullstack** - combining both frontend + backend

---

## The 3 Languages of Frontend

| Language | Full Form | Purpose |
|----------|-----------|---------|
| HTML | HyperText Markup Language | Structure of the webpage |
| CSS | Cascading Style Sheet | Styling & visual appearance |
| JavaScript | - | Behaviour & functionality |

### Simple analogy
> Think of a building:
> - **HTML** = the walls, floors, structure
> - **CSS** = the paint, furniture, decoration
> - **JavaScript** = the electricity, lifts, things that work

---

## How the Web Works

```
CLIENT                          SERVER
(Your Browser)                  (Website's Computer)

    |-------- Request --------->|
    |                           |
    |<-------- Response --------|
    |      (HTML, CSS, JS)      |
    |                           |
  Renders
  the page
```

### Steps:
1. You type a URL in the browser
2. Browser sends a **request** to the server
3. Server sends back **HTML, CSS, JS files** as response
4. Browser **renders** (displays) the page
5. If the page has links to other files, browser sends more requests

---

## URL - Uniform Resource Locator

A URL is the **address** of a resource on the internet.

```
https://www.example.com/about
  |         |              |
protocol   domain         path
```

---

## HTTP vs HTTPS

| | HTTP | HTTPS |
|--|------|-------|
| Full form | HyperText Transfer Protocol | HTTP + Secure |
| Encryption | ❌ No | ✅ Yes |
| Use | Old websites | All modern websites |

- **HTTP** = the language clients and servers use to communicate
- **HTTPS** = same but with **encryption** between client and server
- It is a **text-based** language, not a programming language

---

## Localhost & Port

When you run a website on your own computer:

```
127.0.0.1 : 5500
    |          |
  Your       Port number
 computer's  (web server
  IP address   port)
```

- `127.0.0.1` = IP address of your **local computer**
- `:5500` = the port VS Code Live Server uses
- This is only visible **on your computer**, not the internet

---

## DOM - Document Object Model

- When the browser receives the HTML document from the server, it reads it using the **DOM model**
- The browser makes the DOM using the HTML
- The **model represents the object or element** in the HTML document
- Elements = the building blocks of the page (text, paragraphs, images, links, etc.)

### How the browser renders a page:
1. Browser receives the HTML document
2. Reads through it and finds links to other resources (CSS, images)
3. Sends requests for those resources
4. After having all the resources, it starts **rendering** the page

```
HTML Document
     |
     ▼
  DOM Tree
  (browser builds this)
     |
     ▼
 Rendered Page
 (what you see)
```

---

## DOM — What it can do

The DOM (Document Object Model) is powerful because JavaScript can use it to:

- **Provide interactivity** to the page
- **Add elements** dynamically (e.g. add a new comment to a list)
- **Remove elements** (e.g. delete a card)
- **Access any HTML element** and change it
- **Form validation** — check if inputs are filled correctly before submitting
- **Respond to events** — button clicks, key presses, mouse hover

```
HTML Page
   |
   ▼
Browser builds DOM (tree of all elements)
   |
   ▼
JavaScript can now READ and CHANGE any element
   |
   ▼
Page updates without reloading
```

### Example of what DOM can do:
```javascript
// Change text of an element
document.getElementById("title").innerText = "New Title";

// Add a class
document.getElementById("box").classList.add("highlight");

// Remove an element
document.getElementById("old-item").remove();
```
> You'll learn this when you get to JavaScript — for now just know the DOM is what makes pages interactive.

# Static vs Dynamic Websites

## What is a Static Website?

A **static website** delivers the same pre-built content to every user. The files (HTML, CSS, JS) are stored on a server and served *as-is* — no processing happens on the server before the page is sent to the browser.

### Characteristics
- Content is fixed until a developer manually updates the files
- No server-side processing or database involved
- Faster load times due to pre-built files
- Easier and cheaper to host (e.g., GitHub Pages, Netlify, Vercel)

### Examples
- Portfolio websites
- Documentation pages
- Landing pages

---

## What is a Dynamic Website?

A **dynamic website** generates content on the fly — the server processes requests, fetches data from a database, and builds the page before sending it to the user. Different users (or the same user at different times) may see different content.

### Characteristics
- Content is generated at runtime based on user input, database records, or other logic
- Requires a backend (server + database)
- More complex to build and host
- Supports user authentication, personalization, and real-time data

### Examples
- E-commerce stores (Amazon, Flipkart)
- Social media platforms
- Dashboards and admin panels

---

## Key Differences

| Feature              | Static Website             | Dynamic Website                  |
|----------------------|----------------------------|----------------------------------|
| Content              | Fixed                      | Generated at runtime             |
| Server-side logic    | None                       | Required (PHP, Node.js, Python…) |
| Database             | Not required               | Required                         |
| Load speed           | Generally faster           | Depends on server processing     |
| Hosting cost         | Low (CDN/static hosts)     | Higher (server infrastructure)   |
| Maintenance          | Simple                     | More complex                     |
| Personalization      | Not possible (by default)  | Fully supported                  |
| Examples             | Portfolios, docs, blogs    | Dashboards, e-commerce, social   |

---

## When to Use Which?

- Use a **static website** when content doesn't change often and you want speed, simplicity, and low hosting cost.
- Use a **dynamic website** when you need user logins, database-driven content, or real-time updates.

> **Note:** Modern tools like **Next.js** blur this line — they support *Static Site Generation (SSG)* and *Server-Side Rendering (SSR)*, letting you combine the benefits of both approaches.

---
