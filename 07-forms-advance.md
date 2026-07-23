# 07 - HTML Forms: Basics to Advanced 📝

---

## Why Do We Need Forms?

Forms are the **primary way users interact with websites**.
Without forms, the web would be read-only — you could only look at pages, not do anything.

### Real-world examples of forms:
| Where you see it | What the form does |
|---|---|
| Google Search | Sends your search query |
| Gmail login | Collects email + password |
| Zomato / Swiggy | Takes your delivery address |
| Amazon checkout | Collects payment & address |
| LinkedIn signup | Registers your account |
| Any contact page | Sends a message to the owner |

### Why forms matter for you as a developer:
- Every real project needs at least one form
- Forms connect the **frontend (HTML)** to the **backend (server/database)**
- Understanding forms is required before learning JavaScript events and APIs
- Job interviews often ask you to build a form from scratch

---

## How a Form Works — The Full Picture

```
USER fills in form
        ↓
USER clicks Submit
        ↓
Browser collects all input values
        ↓
Browser sends data to the SERVER (via HTTP request)
        ↓
Server processes data (saves to database, sends email, etc.)
        ↓
Server sends back a RESPONSE
        ↓
Browser shows success/error page
```

Without JavaScript, forms use the `action` and `method` attributes to send data.
With JavaScript, you intercept the submit and handle it yourself (fetch/AJAX).

---

## Part 1 — The `<form>` Tag

The `<form>` tag is the **wrapper** — everything related to data collection goes inside it.

```html
<form action="/submit" method="POST">
  <!-- inputs go here -->
</form>
```

### `action` attribute
Tells the browser **where to send the data** when submitted.

```html
<form action="/contact">        <!-- sends to /contact on same server -->
<form action="submit.php">      <!-- sends to a PHP file -->
<form action="https://api.example.com/data">  <!-- sends to external API -->
<form action="">                <!-- sends to the same current page -->
```

### `method` attribute
Tells the browser **how to send the data**.

```html
<form method="GET">   <!-- data appears in the URL: /search?q=html -->
<form method="POST">  <!-- data is hidden in the request body -->
```

| | GET | POST |
|--|-----|------|
| Data visible? | ✅ Yes — in URL | ❌ No — hidden |
| Use for | Search, filters | Login, payments, sensitive data |
| Bookmarkable? | ✅ Yes | ❌ No |
| Data limit | ~2000 chars | No limit |

### `autocomplete` attribute
```html
<form autocomplete="on">   <!-- browser suggests saved values (default) -->
<form autocomplete="off">  <!-- disable browser suggestions -->
```

### `novalidate` attribute
```html
<form novalidate>   <!-- skips browser's built-in validation — useful when using JS validation -->
```

---

## Part 2 — `<input>` Tag — The Most Used Element

`<input>` is a **self-closing** (void) element — no closing tag needed.
It changes behaviour completely based on the `type` attribute.

### Why type matters:
```html
<input type="text">      <!-- plain text box -->
<input type="email">     <!-- validates email format automatically -->
<input type="password">  <!-- hides characters as you type -->
<input type="number">    <!-- shows number keyboard on mobile -->
<input type="date">      <!-- shows a date picker calendar -->
```

Same tag — completely different behaviour just by changing `type`.

---

### All input types with examples:

#### Text inputs
```html
<!-- Single line text -->
<input type="text" placeholder="Enter your name">

<!-- Email — browser validates format automatically -->
<input type="email" placeholder="you@example.com">

<!-- Password — characters are hidden -->
<input type="password" placeholder="Enter password">

<!-- Number — only allows digits -->
<input type="number" min="1" max="100" step="1">

<!-- Tel — phone number (shows number keyboard on mobile) -->
<input type="tel" placeholder="+91 XXXXX XXXXX">

<!-- URL — validates URL format -->
<input type="url" placeholder="https://yourwebsite.com">

<!-- Search — same as text but styled differently by browser -->
<input type="search" placeholder="Search...">
```

#### Date and time inputs
```html
<!-- Date picker -->
<input type="date">

<!-- Time picker -->
<input type="time">

<!-- Date and time combined -->
<input type="datetime-local">

<!-- Month picker -->
<input type="month">

<!-- Week picker -->
<input type="week">
```

#### Choice inputs
```html
<!-- Checkbox — can select MULTIPLE -->
<input type="checkbox" name="skill" value="html"> HTML
<input type="checkbox" name="skill" value="css"> CSS
<input type="checkbox" name="skill" value="js"> JavaScript

<!-- Radio — can select ONLY ONE (same name groups them) -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female
<input type="radio" name="gender" value="other"> Other

<!-- Range slider -->
<input type="range" min="0" max="100" value="50">

<!-- Color picker -->
<input type="color" value="#ff0000">
```

#### File and hidden inputs
```html
<!-- File upload -->
<input type="file">
<input type="file" accept="image/*">           <!-- images only -->
<input type="file" accept=".pdf,.doc,.docx">   <!-- documents only -->
<input type="file" multiple>                   <!-- allow multiple files -->

<!-- Hidden — not visible but sends data -->
<input type="hidden" name="user_id" value="12345">
```

#### Button inputs
```html
<!-- Submit button — submits the form -->
<input type="submit" value="Send">

<!-- Reset button — clears all fields -->
<input type="reset" value="Clear">

<!-- Plain button — does nothing without JavaScript -->
<input type="button" value="Click Me">
```

---

## Part 3 — Important Input Attributes

```html
<input
  type="text"
  id="username"           <!-- links with <label for="username"> -->
  name="username"         <!-- key name sent to server: username=Aj -->
  value="Aj"              <!-- default pre-filled value -->
  placeholder="Enter name" <!-- hint text shown inside field -->
  required                <!-- field must be filled before submit -->
  disabled                <!-- field is greyed out, cannot be typed in -->
  readonly                <!-- can see but cannot edit -->
  maxlength="50"          <!-- maximum characters allowed -->
  minlength="3"           <!-- minimum characters required -->
  min="1"                 <!-- minimum value (for number/date) -->
  max="100"               <!-- maximum value (for number/date) -->
  step="5"                <!-- increment for number type -->
  pattern="[A-Za-z]+"    <!-- regex pattern the value must match -->
  autocomplete="off"      <!-- disable autocomplete for this field -->
  autofocus               <!-- cursor placed here automatically on page load -->
  multiple                <!-- allow multiple values (email, file) -->
  size="30"               <!-- visible width in characters -->
>
```

### Why `name` is critical
```html
<!-- Without name — data NOT sent to server -->
<input type="text" id="email">

<!-- With name — data IS sent: email=aj@gmail.com -->
<input type="text" id="email" name="email">
```
> The `name` attribute is what the server reads — always include it.

---

## Part 4 — `<label>` Tag

Labels tell users **what each field is for** — essential for accessibility.

### Basic label
```html
<label>Full Name</label>
<input type="text">
```

### Linked label (correct way)
```html
<!-- Method 1: for + id linking -->
<label for="fullname">Full Name</label>
<input type="text" id="fullname">

<!-- Method 2: wrap input inside label -->
<label>
  Full Name
  <input type="text">
</label>
```

### Why linked labels matter:
- Clicking the label **focuses the input** — better UX
- Screen readers announce the label when the input is focused — **accessibility**
- Larger click target on mobile

---

## Part 5 — `<textarea>` — Multi-line Text

Used for longer text like messages, comments, descriptions.

```html
<textarea
  rows="5"
  cols="40"
  placeholder="Write your message here..."
  maxlength="500"
  name="message"
  required
></textarea>
```

| Attribute | Purpose |
|-----------|---------|
| `rows` | Height — number of visible lines |
| `cols` | Width — visible character columns |
| `maxlength` | Maximum characters allowed |
| `placeholder` | Hint text |

### Resize control with CSS
```css
textarea {
  resize: vertical;    /* user can resize height only (recommended) */
  resize: horizontal;  /* user can resize width only */
  resize: both;        /* user can resize both (default) */
  resize: none;        /* disable resize completely */
}
```

---

## Part 6 — `<select>` — Dropdown Menu

```html
<select name="course" id="course">
  <option value="">-- Select a course --</option>   <!-- placeholder option -->
  <option value="html">HTML</option>
  <option value="css" selected>CSS</option>          <!-- pre-selected -->
  <option value="js" disabled>JavaScript (coming soon)</option>
</select>
```

### Option groups
```html
<select name="language">
  <optgroup label="Frontend">
    <option value="html">HTML</option>
    <option value="css">CSS</option>
    <option value="js">JavaScript</option>
  </optgroup>
  <optgroup label="Backend">
    <option value="python">Python</option>
    <option value="node">Node.js</option>
  </optgroup>
</select>
```

### Multi-select
```html
<!-- Hold Ctrl/Cmd to select multiple -->
<select name="skills" multiple size="4">
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
  <option value="python">Python</option>
</select>
```

---

## Part 7 — `<button>` Tag

More flexible than `<input type="submit">` — can contain HTML inside.

```html
<!-- Submit form (default type inside a form) -->
<button type="submit">Submit</button>

<!-- Reset all fields -->
<button type="reset">Clear</button>

<!-- Plain button — needs JavaScript to do anything -->
<button type="button">Click Me</button>

<!-- Button with icon inside -->
<button type="submit">
  <img src="send-icon.svg" alt=""> Send Message
</button>
```

> Always specify `type` on buttons inside forms. Without it,
> browsers default to `type="submit"` which may submit the form unexpectedly.

---

## Part 8 — `<fieldset>` and `<legend>` — Grouping

Used to visually and logically group related fields together.

```html
<form>
  <fieldset>
    <legend>Personal Information</legend>
    <label for="fname">First Name</label>
    <input type="text" id="fname" name="fname">

    <label for="lname">Last Name</label>
    <input type="text" id="lname" name="lname">
  </fieldset>

  <fieldset>
    <legend>Account Details</legend>
    <label for="email">Email</label>
    <input type="email" id="email" name="email">

    <label for="pass">Password</label>
    <input type="password" id="pass" name="pass">
  </fieldset>
</form>
```

### Why use fieldset:
- Groups related fields visually (draws a box around them)
- Screen readers announce the group name
- Can `disabled` an entire group at once:
```html
<fieldset disabled>
  <!-- all inputs inside are disabled -->
</fieldset>
```

---

## Part 9 — `<datalist>` — Input with Suggestions

Combines free text input with dropdown suggestions — user can type OR choose.

```html
<label for="browser">Favourite Browser:</label>
<input type="text" id="browser" name="browser" list="browsers">

<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
  <option value="Edge">
  <option value="Brave">
</datalist>
```

> Unlike `<select>`, the user can also type something not in the list.

---

## Part 10 — HTML5 Built-in Validation

Browsers can validate forms automatically — no JavaScript needed for basic checks.

```html
<form>
  <!-- Required field -->
  <input type="text" name="name" required>

  <!-- Email format check -->
  <input type="email" name="email" required>

  <!-- Minimum and maximum length -->
  <input type="text" name="username" minlength="3" maxlength="20" required>

  <!-- Number range -->
  <input type="number" name="age" min="18" max="60" required>

  <!-- Custom pattern using regex -->
  <!-- Only letters, 3-10 chars -->
  <input
    type="text"
    name="code"
    pattern="[A-Za-z]{3,10}"
    title="Only letters, 3 to 10 characters"
    required
  >

  <!-- URL format -->
  <input type="url" name="website" required>

  <button type="submit">Submit</button>
</form>
```

### How browser validation works:
1. User clicks Submit
2. Browser checks each field from top to bottom
3. First invalid field gets focused and an error tooltip appears
4. Form does NOT submit until all fields are valid

### Styling valid/invalid fields with CSS
```css
/* Field is valid */
input:valid {
  border: 2px solid green;
}

/* Field is invalid (only shows after user interacts) */
input:invalid {
  border: 2px solid red;
}

/* Required field that hasn't been filled */
input:required {
  border-left: 4px solid orange;
}

/* Optional field */
input:optional {
  border-left: 4px solid #ccc;
}

/* Disabled field */
input:disabled {
  background-color: #f0f0f0;
  cursor: not-allowed;
}
```

---

## Part 11 — Styling Forms with CSS

```css
/* Reset default browser styles */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

/* Form container */
form {
  max-width: 500px;
  margin: 40px auto;
  padding: 30px;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

/* Labels */
label {
  display: block;
  margin-bottom: 6px;
  font-weight: 600;
  color: #333;
  font-size: 14px;
}

/* All inputs, textareas, selects */
input,
textarea,
select {
  width: 100%;
  padding: 10px 14px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 15px;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
  outline: none;
}

/* Focus state — highlight when typing */
input:focus,
textarea:focus,
select:focus {
  border-color: #4CAF50;
  box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.2);
}

/* Submit button */
button[type="submit"] {
  width: 100%;
  padding: 12px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s ease, transform 0.1s ease;
}

button[type="submit"]:hover {
  background-color: #45a049;
  transform: translateY(-1px);
}

button[type="submit"]:active {
  transform: translateY(0);
}
```

---

## Part 12 — Complete Examples

### Example 1 — Basic Contact Form
```html
<!DOCTYPE html>
<html>
<head>
  <title>Contact Form</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f0f2f5; }
    form { max-width: 500px; margin: 40px auto; padding: 30px; background: white; border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
    h2 { margin-bottom: 20px; color: #333; }
    label { display: block; margin-bottom: 5px; font-weight: bold; color: #555; }
    input, textarea, select { width: 100%; padding: 10px; margin-bottom: 16px; border: 1px solid #ddd; border-radius: 5px; font-size: 14px; box-sizing: border-box; }
    input:focus, textarea:focus { border-color: #4CAF50; outline: none; }
    button { width: 100%; padding: 12px; background: #4CAF50; color: white; border: none; border-radius: 5px; font-size: 16px; cursor: pointer; }
    button:hover { background: #45a049; }
  </style>
</head>
<body>
  <form action="/contact" method="POST">
    <h2>Contact Me</h2>

    <label for="name">Full Name *</label>
    <input type="text" id="name" name="name" placeholder="Enter your name" required>

    <label for="email">Email Address *</label>
    <input type="email" id="email" name="email" placeholder="you@example.com" required>

    <label for="subject">Subject</label>
    <select id="subject" name="subject">
      <option value="">-- Select subject --</option>
      <option value="job">Job Opportunity</option>
      <option value="collab">Collaboration</option>
      <option value="general">General Query</option>
    </select>

    <label for="message">Message *</label>
    <textarea id="message" name="message" rows="5" placeholder="Write your message..." required></textarea>

    <button type="submit">Send Message</button>
  </form>
</body>
</html>
```

---

### Example 2 — Registration Form with Validation
```html
<!DOCTYPE html>
<html>
<head>
  <title>Registration Form</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f5f5f5; }
    form { max-width: 550px; margin: 30px auto; padding: 30px; background: white; border-radius: 10px; box-shadow: 0 2px 15px rgba(0,0,0,0.1); }
    h2 { text-align: center; margin-bottom: 25px; color: #333; }
    fieldset { border: 1px solid #ddd; border-radius: 8px; padding: 20px; margin-bottom: 20px; }
    legend { font-weight: bold; color: #4CAF50; padding: 0 8px; font-size: 15px; }
    label { display: block; margin-bottom: 5px; font-weight: 600; color: #555; font-size: 14px; }
    input, select { width: 100%; padding: 10px; margin-bottom: 14px; border: 1px solid #ddd; border-radius: 5px; font-size: 14px; box-sizing: border-box; transition: border 0.2s; }
    input:focus, select:focus { border-color: #4CAF50; outline: none; }
    input:valid { border-color: #4CAF50; }
    input:invalid:not(:placeholder-shown) { border-color: #e74c3c; }
    .radio-group { display: flex; gap: 20px; margin-bottom: 14px; }
    .radio-group label { font-weight: normal; display: flex; align-items: center; gap: 6px; }
    .radio-group input { width: auto; margin: 0; }
    .checkbox-label { display: flex; align-items: center; gap: 8px; font-weight: normal; margin-bottom: 20px; }
    .checkbox-label input { width: auto; margin: 0; }
    button { width: 100%; padding: 13px; background: #4CAF50; color: white; border: none; border-radius: 5px; font-size: 16px; cursor: pointer; font-weight: bold; }
    button:hover { background: #388e3c; }
  </style>
</head>
<body>
  <form action="/register" method="POST" novalidate>
    <h2>Create Account</h2>

    <fieldset>
      <legend>Personal Details</legend>

      <label for="fname">First Name *</label>
      <input type="text" id="fname" name="fname" placeholder="Gagan" minlength="2" required>

      <label for="lname">Last Name *</label>
      <input type="text" id="lname" name="lname" placeholder="AJ" minlength="1" required>

      <label for="dob">Date of Birth *</label>
      <input type="date" id="dob" name="dob" required>

      <label>Gender *</label>
      <div class="radio-group">
        <label><input type="radio" name="gender" value="male" required> Male</label>
        <label><input type="radio" name="gender" value="female"> Female</label>
        <label><input type="radio" name="gender" value="other"> Other</label>
      </div>
    </fieldset>

    <fieldset>
      <legend>Account Details</legend>

      <label for="email">Email Address *</label>
      <input type="email" id="email" name="email" placeholder="you@example.com" required>

      <label for="phone">Phone Number</label>
      <input type="tel" id="phone" name="phone" placeholder="+91 XXXXX XXXXX" pattern="[0-9]{10}">

      <label for="password">Password *</label>
      <input type="password" id="password" name="password" placeholder="Min 8 characters" minlength="8" required>

      <label for="confirm">Confirm Password *</label>
      <input type="password" id="confirm" name="confirm" placeholder="Repeat password" required>
    </fieldset>

    <fieldset>
      <legend>Preferences</legend>

      <label for="course">Primary Skill *</label>
      <select id="course" name="course" required>
        <option value="">-- Select skill --</option>
        <optgroup label="Frontend">
          <option value="html">HTML & CSS</option>
          <option value="js">JavaScript</option>
          <option value="react">React</option>
        </optgroup>
        <optgroup label="Backend">
          <option value="python">Python</option>
          <option value="node">Node.js</option>
        </optgroup>
      </select>

      <label for="experience">Experience (years)</label>
      <input type="range" id="experience" name="experience" min="0" max="10" value="1">

      <label>Interests (select all that apply)</label>
      <label><input type="checkbox" name="interest" value="web"> Web Development</label>
      <label><input type="checkbox" name="interest" value="data"> Data Analytics</label>
      <label><input type="checkbox" name="interest" value="cloud"> Cloud Computing</label>
    </fieldset>

    <label class="checkbox-label">
      <input type="checkbox" name="terms" required>
      I agree to the Terms and Conditions *
    </label>

    <button type="submit">Create Account</button>
  </form>
</body>
</html>
```

---

### Example 3 — Advanced: Form with JavaScript Validation
```html
<!DOCTYPE html>
<html>
<head>
  <title>Advanced Form with JS Validation</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f0f2f5; }
    form { max-width: 480px; margin: 40px auto; padding: 30px; background: white; border-radius: 10px; box-shadow: 0 4px 20px rgba(0,0,0,0.1); }
    h2 { text-align: center; margin-bottom: 24px; }
    .field { margin-bottom: 18px; }
    label { display: block; margin-bottom: 5px; font-weight: bold; font-size: 14px; }
    input { width: 100%; padding: 10px 14px; border: 1px solid #ddd; border-radius: 6px; font-size: 15px; box-sizing: border-box; outline: none; transition: border 0.2s; }
    input:focus { border-color: #3498db; }
    .error { color: #e74c3c; font-size: 12px; margin-top: 4px; display: none; }
    .error.show { display: block; }
    input.invalid { border-color: #e74c3c; }
    input.valid { border-color: #2ecc71; }
    button { width: 100%; padding: 12px; background: #3498db; color: white; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; margin-top: 10px; }
    button:hover { background: #2980b9; }
    .success { display: none; text-align: center; padding: 15px; background: #d5f5e3; border-radius: 6px; color: #27ae60; font-weight: bold; margin-top: 15px; }
  </style>
</head>
<body>
  <form id="myForm" novalidate>
    <h2>Login Form</h2>

    <div class="field">
      <label for="email">Email Address</label>
      <input type="email" id="email" placeholder="you@example.com">
      <div class="error" id="email-error">Please enter a valid email address.</div>
    </div>

    <div class="field">
      <label for="pass">Password</label>
      <input type="password" id="pass" placeholder="Min 8 characters">
      <div class="error" id="pass-error">Password must be at least 8 characters.</div>
    </div>

    <button type="submit">Login</button>
    <div class="success" id="success-msg">✅ Login successful! Welcome back.</div>
  </form>

  <script>
    const form = document.getElementById('myForm');
    const emailInput = document.getElementById('email');
    const passInput = document.getElementById('pass');

    function showError(input, errorId) {
      input.classList.add('invalid');
      input.classList.remove('valid');
      document.getElementById(errorId).classList.add('show');
    }

    function showValid(input, errorId) {
      input.classList.add('valid');
      input.classList.remove('invalid');
      document.getElementById(errorId).classList.remove('show');
    }

    form.addEventListener('submit', function(e) {
      e.preventDefault();   // stop default form submission
      let isValid = true;

      // Validate email
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailRegex.test(emailInput.value)) {
        showError(emailInput, 'email-error');
        isValid = false;
      } else {
        showValid(emailInput, 'email-error');
      }

      // Validate password
      if (passInput.value.length < 8) {
        showError(passInput, 'pass-error');
        isValid = false;
      } else {
        showValid(passInput, 'pass-error');
      }

      // If all valid — show success
      if (isValid) {
        document.getElementById('success-msg').style.display = 'block';
      }
    });
  </script>
</body>
</html>
```

---

## Part 13 — Quick Reference: When to Use What

| Situation | Use |
|-----------|-----|
| Single line text | `<input type="text">` |
| Email address | `<input type="email">` |
| Password | `<input type="password">` |
| Phone number | `<input type="tel">` |
| Long message | `<textarea>` |
| One choice from list | `<input type="radio">` |
| Multiple choices | `<input type="checkbox">` |
| Dropdown list | `<select>` |
| Dropdown + free text | `<input> + <datalist>` |
| Date picker | `<input type="date">` |
| File upload | `<input type="file">` |
| Number with slider | `<input type="range">` |
| Color picker | `<input type="color">` |
| Hidden data | `<input type="hidden">` |
| Group related fields | `<fieldset> + <legend>` |
| Submit form | `<button type="submit">` |

---

## Part 14 — Common Mistakes to Avoid

```html
<!-- ❌ WRONG — no name attribute, data won't be sent -->
<input type="text" id="email">

<!-- ✅ CORRECT -->
<input type="text" id="email" name="email">

---

<!-- ❌ WRONG — label not linked to input -->
<label>Name</label>
<input type="text">

<!-- ✅ CORRECT -->
<label for="name">Name</label>
<input type="text" id="name" name="name">

---

<!-- ❌ WRONG — button without type inside form (will submit) -->
<button onclick="doSomething()">Click</button>

<!-- ✅ CORRECT -->
<button type="button" onclick="doSomething()">Click</button>

---

<!-- ❌ WRONG — radio buttons with different names (won't group) -->
<input type="radio" name="gender1" value="male"> Male
<input type="radio" name="gender2" value="female"> Female

<!-- ✅ CORRECT — same name groups them -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female
```

---

## Summary

```
FORM STRUCTURE
  <form action="" method="">    ← wrapper, where to send, how to send
    <fieldset> + <legend>       ← group related fields
    <label for="id">            ← always link labels to inputs
    <input type="">             ← the main element, 20+ types
    <textarea>                  ← multi-line text
    <select> + <option>         ← dropdown
    <datalist>                  ← suggestions with free text
    <button type="submit">      ← submit the form

KEY ATTRIBUTES
  name       → server reads this (required for data to be sent)
  id         → links label to input
  required   → makes field mandatory
  placeholder → hint text
  value      → default/pre-filled value
  disabled   → field cannot be edited
  pattern    → regex validation

VALIDATION
  HTML5 built-in  → required, min, max, pattern, type
  CSS pseudo      → :valid, :invalid, :required, :disabled
  JavaScript      → e.preventDefault(), custom error messages
```
