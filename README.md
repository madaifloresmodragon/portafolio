<img src="https://www.w3.org/html/logo/downloads/HTML5_Badge.svg" alt="HTML5 Logo" width="100">

# 🧩 HTML Style Guide

Welcome to the HTML Style Guide.

This guide promotes the use of consistent, clean and orderly HTML code. Its purpose is to facilitate the reading and understanding of the code, as well as to encourage good practices that will improve its maintenance and reuse in the future.

> _Every line of code should appear to be written by a single person, no matter the number of contributors._

---

## 📌 Table of Contents
1. [File Structure](#file-structure)  
2. [Coding and DOCTYPE](#coding-and-doctype)  
3. [Indentation and Spacing](#indentation-and-spacing)  
4. [Comments](#comments)  
5. [Attributes](#attributes)  
    5.1. [Names in lowercase](#names-in-lowercase)  
    5.2. [Attribute values](#attribute-values)  
    5.3. [alt, width and height for images](#alt-width-and-height-for-images)  
    5.4. [Attribute order](#attribute-order)  
    5.5. [Spaces and equal signs](#spaces-and-equal-signs)  
    5.6. [Identifiers for interactive elements](#identifiers-for-interactive-elements)  
6. [HTML Performance](#html-performance)  
    6.1. [Loading scripts and styles](#loading-scripts-and-styles)  
    6.2. [Minimization of markup](#minimization-of-markup)  
7. [Best practices and SEO](#best-practices-and-seo)
    7.1. [Semantic HTML](#semantic-html)
    7.2. [Meta tags](#meta-tags)
    7.3. [Accessibility and ARIA](#accessibility-and-aria) 
8. [HTML Base Code](#html-base-code)  

---

## File Structure
- Files must have `.html` extension
- Use **kebab-case** filenames (hyphens and lowercase)

🔴 __Bad:__

~~~
UserProfile.HTML
userProfile.html
~~~

🟢 __Good:__

~~~
user-profile.html
~~~

---

## Coding and DOCTYPE

- Always use `UTF-8` for character encoding.
- Declare the document type as `<!DOCTYPE html>`.

🔴 __Bad:__

~~~
<DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="" />
    <title>My Page</title>
  </head>
  <body></body>
</html>
~~~

🟢 __Good:__

~~~
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My Page</title>
  </head>
  <body></body>
</html>
~~~

---

## Indentation and Spacing

- Use **2-space** soft tabs for indentation.
- Each nested level must be **well indented**.
- Separate the block element with a blank line and group the internal block elements.

🔴 __Bad:__

~~~
<ul class="nav-tabs">

  <li>...</li>

  <li>...</li>

  <li>...</li>

  <li>...</li>

</ul>
<div class="tab-content">
  ...
</div>
~~~

🟢 __Good:__

~~~
<ul class="nav-tabs">
  <li>...</li>
  <li>...</li>
  <li>...</li>
  <li>....</li>
</ul>

<div class="tab-content">
  ...
</div>
~~~

---

## Comments

- Use comments for **important sections** or **large blocks**
- Follow the proper format for HTML comments

🔴 __Bad:__

~~~
<!--This is a poorly formatted comment-->
~~~

🟢 __Good:__
~~~
<!-- This is a small comment -->

<!--
  This block explains the main navigation section.
  This block explains the main navigation section.
-->
~~~

---

## Attributes

### Names in lowercase
- Use lowercase attribute names

🔴 __Bad:__
~~~
<a HREF="#">Example</a>
~~~

🟢 __Good:__
~~~
<a href="#">Example</a>
~~~

### Attribute values
- Use **double quotation marks** `" "` for values
- Use **kebab-case** for the values

🔴 __Bad:__
~~~
<section class='userSection' id=section_one>
  section content goes here
</section> 
~~~

🟢 __Good:__
~~~
<section class="user-section" id="user-section">
  section content goes here
</section> 
~~~

### alt, width and height for images

- Always specify **alt** attribute for images
- `alt` must be descriptive of the image content for accessibility.
- Define the **width** and **height** of the images

🔴 __Bad:__
~~~
<img src="html5.png">
~~~

🟢 __Good:__
~~~
<img src="html5.png" alt="HTML5" width="128" height="128">
~~~

### Attribute order

- Attributes go on a **single line** if there are few of them
- The HTML attributes must be in this order to facilitate reading:
    1. class
    2. id, name
    3. data-*
    4. src, for, type, href
    5. title, alt
    6. aria-*, role

🔴 __Bad:__

~~~
<a href="#contact" id="contact-btn" class="btn" title="Contact">
  Contact us at
</a>
~~~

🟢 __Good:__
~~~
<a class="btn" id="contact-btn" href="#contact" title="Contact">
  Contact us at
</a>

<img class="logo" src="logo.png" alt="Company logo">
~~~

### Spaces and equal signs
- Avoid gaps around the equal **`=`**
- The absence of spaces facilitates reading and improves the grouping of the entities.

🔴 __Bad:__

~~~
<link rel = "stylesheet" href = "styles.css">
~~~

🟢 __Good:__
~~~
<link rel="stylesheet" href="styles.css">
~~~

### Identifiers for interactive elements
- Assign a meaningful **`id`** or **`class`** to **interactive elements** such as:
  + Buttons
  + Links
  + Inputs
  + Forms
- The **`id`** must be **`unique`** on the page
- Prefer **`class`** to apply styles and **`id`** to identify uniquely

🔴 __Bad:__

~~~
<button>Send</button>

<a href="/">Home</a>

<input type="email">
~~~

🟢 __Good:__
~~~
<button class="btn-submit" id="submit-form">Send</button>

<a class="nav-link" id="home-link" href="/">Home</a>

<input type="email" id="user-email" class="input-field">
~~~

📍 __Council:__ 
>_If an element can be clicked or used in tests, **always assign a class or id with a descriptive name.**_

---

## HTML Performance

### Loading scripts and styles
- Use `<link rel="stylesheet">` for external CSS
- Use the `<script>` just before`</body>` unless it's `type="module"` or you need to load it before

🔴 __Bad:__

~~~
<head>
  <link rel="stylesheet" href="styles.css">
  <script src="app.js"></script>
</head>
<body>
  ...
</body>
~~~

🟢 __Good:__

~~~
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  ...
  <script src="app.js"></script>
</body>
~~~

---
### Minimization of markup
- Avoid unnecessary containers
- Keep HTML clean and purposeful

🔴 __Bad:__

~~~
<div>
  <div>
    <div class="container">
      <h1>Welcome to</h1>
    </div>
  </div>
</div>
~~~

🟢 __Good:__

~~~
<div class="container">
  <h1>Welcome to</h1>
</div>
~~~

---

## Best practices and SEO

### Semantic HTML

- Use semantic tags (`<header>`, `<section>`, `<main>`, `<article>`, `<footer>`)
- Use headings (`<h1>` to `<h6>`) in a hierarchical way.
- Avoid duplicate content and unnecessary nesting

🔴 __Bad:__

~~~
<!DOCTYPE html>
<html>
<head>
  <title>User Profile</title>
</head>
<body>
  <div>
    <div>User Profile</div>
  </div>
  <div>
    <div>Personal Information</div>
  </div>
  <div>
    <p>© 2025 Company</p>
  </div>
</body>
</html>
~~~

🟢 __Good:__

~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>User Profile</title>
</head>
<body>
  <header>
    <h1>User Profile</h1>
  </header>
  <main>
    <section>
      <h2>Personal Information</h2>
    </section>
  </main>
  <footer>
    <p>© 2025 Company</p>
  </footer>
</body>
</html>
~~~

### Meta tags

- Add a `lang` attribute to `<html>`
- Use metadata: `<meta name="description" content="...">`

🔴 __Bad:__

~~~
<!DOCTYPE html>
<html>
<head>
  <title>User Profile</title>
</head>
<body>
  <!-- Content -->
</body>
</html>
~~~

🟢 __Good:__

~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="description" content="User profile page with contact and configuration sections" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>User Profile</title>
</head>
<body>
  <!-- Content -->
</body>
</html>
~~~

### Accessibility and ARIA

- Always define `alt` on images
- Use semantic elements `(e.g., <button>, <nav>)`.
- When using non-semantic elements, add **ARIA** attributes `(role, aria-label, aria-hidden, etc.)` to describe their function and improve navigation.
- **Avoid complex structures** that make comprehension or keyboard navigation difficult.

🔴 __Bad:__

~~~
<!DOCTYPE html>
<html>
<head>
  <title>Accessible User Profile</title>
</head>
<body>
  <img src="profile.jpg" />
  
  <div>
    <ul>
      <li><a href="#profile">Profile</a></li>
      <li><a href="#settings">Settings</a></li>
    </ul>
  </div>

  <div>Submit</div>
</body>
</html>
~~~

🟢 __Good:__
~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Accessible User Profile</title>
</head>
<body>
  <img src="profile.jpg" alt="User profile picture" />
  
  <nav role="navigation" aria-label="Main menu">
    <ul>
      <li><a href="#profile">Profile</a></li>
      <li><a href="#settings">Settings</a></li>
    </ul>
  </nav>

  <button aria-label="Submit form">Submit</button>
</body>
</html>
~~~

---

## HTML Base Code
- Use the following code as a HTML base to start projects faster

🟢 __Good:__
~~~
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Project</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header class="main-header">
    <h1>Welcome</h1>
  </header>

  <main class="main-content">
    <!-- Main content -->
  </main>

  <footer class="main-footer">
    <p>&copy; 2025 My project</p>
  </footer>

  <script src="main.js"></script>
</body>
</html>
~~~
