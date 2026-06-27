# 07 - Forms 📝

## What is a Form?
- Forms are used to **collect information from users**
- Login pages, signup pages, contact pages — all use forms
- The `<form>` tag wraps all form elements

---

## Basic Form Structure

```html
<form>
  <!-- all form elements go here -->
</form>
```

---

## `<input>` tag

The most used form element. It has **many types**:

```html
<input type="text">       <!-- single line text box -->
<input type="email">      <!-- email field -->
<input type="password">   <!-- hides what you type -->
<input type="number">     <!-- numbers only -->
<input type="checkbox">   <!-- tick box -->
<input type="radio">      <!-- choose one option -->
<input type="file">       <!-- upload a file -->
<input type="date">       <!-- date picker -->
<input type="submit">     <!-- submit button -->
```

---

## `<label>` tag

Labels tell the user **what to type** in each field:

```html
<label>Name:</label>
<input type="text">
```

### Better way — link label to input using `for` and `id`:
```html
<label for="username">Name:</label>
<input type="text" id="username">
```
Now clicking the label also focuses the input — better UX!

---

## `<textarea>` — Multi-line Text

For longer text like messages or comments:

```html
<textarea rows="5" cols="40">
  Default text here...
</textarea>
```

---

## `<select>` — Dropdown Menu

```html
<select>
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
</select>
```

---

## `<button>` tag

```html
<button>Click Me</button>
<button type="submit">Submit Form</button>
<button type="reset">Clear Form</button>
```

---

## Important Input Attributes

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `type` | What kind of input | `type="email"` |
| `placeholder` | Hint text inside field | `placeholder="Enter name"` |
| `name` | Identifies the field | `name="username"` |
| `id` | Links with label | `id="username"` |
| `required` | Makes field mandatory | `required` |
| `value` | Default value | `value="John"` |

---

## Full Form Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Contact Form</title>
    <style>
      form {
        max-width: 400px;
        margin: 20px auto;
      }
      label {
        display: block;
        margin-top: 12px;
        font-weight: bold;
      }
      input, textarea, select {
        width: 100%;
        padding: 8px;
        margin-top: 4px;
        border: 1px solid #ccc;
        border-radius: 4px;
      }
      button {
        margin-top: 16px;
        padding: 10px 20px;
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
      }
    </style>
  </head>
  <body>

    <h2>Contact Us</h2>

    <form>

      <label for="name">Full Name:</label>
      <input type="text" id="name" placeholder="Enter your name" required>

      <label for="email">Email:</label>
      <input type="email" id="email" placeholder="Enter your email" required>

      <label for="password">Password:</label>
      <input type="password" id="password" placeholder="Enter password">

      <label for="age">Age:</label>
      <input type="number" id="age" placeholder="Enter your age">

      <label for="course">Choose Course:</label>
      <select id="course">
        <option value="html">HTML</option>
        <option value="css">CSS</option>
        <option value="js">JavaScript</option>
      </select>

      <label for="message">Message:</label>
      <textarea id="message" rows="4" placeholder="Write your message..."></textarea>

      <label>
        <input type="checkbox"> I agree to the terms
      </label>

      <button type="submit">Submit</button>
      <button type="reset">Clear</button>

    </form>

  </body>
</html>
```

---

## Checkbox vs Radio Button

```html
<!-- Checkbox — can select MULTIPLE -->
<input type="checkbox" name="skill" value="html"> HTML
<input type="checkbox" name="skill" value="css"> CSS
<input type="checkbox" name="skill" value="js"> JavaScript

<!-- Radio — can select ONLY ONE (same name groups them) -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female
```
