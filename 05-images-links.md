# 05 - Images & Links 🖼️🔗

## Images — `<img>` tag

### Basic syntax:
```html
<img src="image.jpg" alt="description of image">
```

### Important things about `<img>`:
- It has **no closing tag** — it is a self-closing tag
- It has **no child elements**
- It uses **attributes** to work (`src` and `alt`)

---

## Image Attributes

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `src` | Source — where the image file is | `src="photo.jpg"` |
| `alt` | Alternate text — shown if image fails to load | `alt="My photo"` |
| `width` | Width of image | `width="200px"` |
| `height` | Height of image | `height="100px"` |

```html
<!-- Basic image -->
<img src="photo.jpg" alt="My photo">

<!-- Image with size -->
<img src="logo.png" alt="Company logo" width="200px" height="100px">

<!-- Image from internet (absolute URL) -->
<img src="https://example.com/image.jpg" alt="Online image">
```

---

## Styling Images with CSS

```html
<style>
  img {
    width: 300px;
    border-radius: 10px;
    border: 2px solid black;
  }

  .profile-pic {
    width: 150px;
    border-radius: 50%;   /* makes it a circle */
  }
</style>

<img src="photo.jpg" alt="Profile" class="profile-pic">
```

---

## File Paths

### Relative path (file is in your project folder)
```html
<!-- Image is in the SAME folder as your HTML file -->
<img src="photo.jpg" alt="Photo">

<!-- Image is in an 'images' folder inside your project -->
<img src="images/photo.jpg" alt="Photo">

<!-- Go UP one folder then into images -->
<img src="../images/photo.jpg" alt="Photo">
```

### Absolute path (full URL from internet)
```html
<img src="https://www.example.com/photo.jpg" alt="Photo">
```

---

## Links — `<a>` tag (Anchor Tag)
- Anchor tag is used to navigate the web pages from current page
- The `<a>` tag creates a **clickable link**:

```html
<a href="https://www.google.com">Click here to go to Google</a>
```

### Link attributes:

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `href` | Where the link goes | `href="https://google.com"` |
| `target` | How to open the link | `target="_blank"` |

---

## Types of Links

### External link (goes to another website)
```html
<a href="https://www.google.com">Go to Google</a>
```

### Internal link (goes to another page in YOUR project)
```html
<a href="about.html">Go to About page</a>
<a href="pages/contact.html">Go to Contact page</a>
```

### Link to a section on the SAME page
```html
<!-- The link -->
<a href="#about-section">Jump to About</a>

<!-- The target section -->
<h2 id="about-section">About Me</h2>
```

---

## target="_blank"

Opens the link in a **new browser tab**:

```html
<!-- Opens in same tab (default) -->
<a href="https://google.com">Google</a>

<!-- Opens in NEW tab -->
<a href="https://google.com" target="_blank">Google</a>
```

---

## Image as a Link

Wrap an `<img>` inside an `<a>` tag:

```html
<a href="https://google.com">
  <img src="google-logo.png" alt="Go to Google">
</a>
```

---

## Full Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Images and Links</title>
    <style>
      img {
        width: 300px;
        border-radius: 8px;
      }
      a {
        color: blue;
        text-decoration: none;   /* removes underline */
      }
      a:hover {
        text-decoration: underline;  /* underline on hover */
      }
    </style>
  </head>
  <body>

    <h1>My Profile</h1>

    <img src="profile.jpg" alt="My profile picture">

    <p>Visit my favourite site:
      <a href="https://google.com" target="_blank">Google</a>
    </p>

    <p>
      <a href="about.html">About Me</a> |
      <a href="contact.html">Contact</a>
    </p>

  </body>
</html>
```

---

## Advanced Anchor Features

### mailto: link — opens email app
```html
<a href="mailto:aj@gmail.com">Email Me</a>
```
- This is called a **hyperlink** — we can call links by this name overall
- Clicking it opens the user's default email app

### Download link — downloads a file
```html
<a href="file.pdf" download>Download PDF</a>

<!-- Download an image -->
<a href="photo.jpg" download>Download Image</a>
```

### Link to a section on same page using `#`
```html
<!-- Navigation link -->
<a href="#about">Go to About section</a>

<!-- Target section (must match the id) -->
<h2 id="about">About Me</h2>
```
- The `#` targets the **ID** of an element on the same page
- You can also use `#` as a placeholder: `<a href="#">Click</a>` goes nowhere

### All anchor attributes together
```html
<a 
  href="https://google.com"   
  target="_blank"              
  download                     
>
  Link text
</a>
```

| Attribute | Purpose |
|-----------|---------|
| `href` | Where the link goes (URL / relative / `#id` / `mailto:`) |
| `target="_blank"` | Opens in new tab |
| `download` | Downloads the file instead of opening it |

---

## object-fit — CSS for Images

Used when you want an image to fill a box without stretching:

```css
img {
  width: 300px;
  height: 200px;
  object-fit: cover;   /* fills the box, crops if needed */
}
```
 
| Value | What it does |
|-------|-------------|
| `cover` | Fills the box, may crop edges — most used |
| `contain` | Fits whole image inside box, may leave gaps |
| `fill` | Stretches image to fill — looks bad usually |
| `none` | Keeps original size |

```css
/* Common use — profile pictures, card images */
.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.profile-pic {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
}
```
