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
