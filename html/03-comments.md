## Table of Contents

- [Introduction](#introduction)
- [Comment Syntax](#comment-syntax)
- [Uses of HTML Comments](#uses-of-html-comments)
- [Commenting Out HTML Code](#commenting-out-html-code)
- [Important Rules](#important-rules)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


# HTML Comments

## Introduction

HTML comments are pieces of text written inside an HTML document that are **ignored by web browsers**. They are not displayed on the webpage and are mainly used to add notes, explanations, or reminders for developers.

Comments improve the readability and maintainability of code, especially when working on large projects or collaborating with other developers.

---

## Comment Syntax

HTML comments begin with `<!--` and end with `-->`.

### Example

```html
<!-- This is an HTML comment -->

<h1>Welcome</h1>

<!-- This paragraph introduces the website -->
<p>This is my first webpage.</p>
```

Everything written between `<!--` and `-->` is treated as a comment and is not displayed in the browser.


---


## Uses of HTML Comments

HTML comments help developers write cleaner, more understandable, and maintainable code. Since comments are ignored by browsers, they are only visible in the source code.

Common uses of HTML comments include:

- Explaining complex sections of code.
- Adding notes or reminders for yourself or other developers.
- Organizing different sections of a webpage.
- Temporarily disabling HTML code during testing or debugging.

### Example: Section Comments

```html
<!-- Header Section -->
<header>
    <h1>My Website</h1>
</header>

<!-- Main Content -->
<main>
    <p>Welcome to my website.</p>
</main>

<!-- Footer Section -->
<footer>
    <p>&copy; 2026 My Website</p>
</footer>
```


---


## Commenting Out HTML Code

Comments can also be used to temporarily disable HTML code without deleting it.

### Example

```html
<!--
<p>This paragraph will not be displayed.</p>
-->

<h1>Visible Heading</h1>
```

This is useful while testing layouts or debugging webpages.


---


## Important Rules

- Comments start with `<!--` and end with `-->`.
- Comments are not displayed in the browser.
- Comments can span multiple lines.
- Avoid placing confidential or sensitive information inside comments because anyone can view the page source.
- Use comments only when they improve code readability. Too many unnecessary comments can make code harder to maintain.


---


## Key Takeaways

- HTML comments are ignored by web browsers and are not displayed on the webpage.
- Comments begin with `<!--` and end with `-->`.
- They help explain code, organize sections, and leave notes for developers.
- Comments can be used to temporarily disable HTML code during testing or debugging.
- Avoid storing passwords, API keys, or other sensitive information in comments because anyone can view the page source.
- Use comments only when they improve code readability and maintainability.


---


## References

To learn more about HTML comments, refer to the following resources:

- **MDN Web Docs** – HTML Comments
- **WHATWG HTML Living Standard**
- **W3Schools HTML Comments Tutorial**


---


## Quick Revision

| Topic | Description |
|--------|-------------|
| HTML Comment | Text ignored by the browser and not displayed on the webpage. |
| Syntax | `<!-- Comment -->` |
| Purpose | Add notes, explanations, reminders, or temporarily disable HTML code. |
| Visibility | Visible only in the HTML source code. |
| Browser Behavior | Browsers ignore comments while rendering the webpage. |

### Example

```html
<!-- This is an HTML comment -->

<h1>Welcome</h1>

<!-- This paragraph is temporarily disabled -->
<!--
<p>Hello World!</p>
-->
```

### Remember

- HTML comments start with `<!--` and end with `-->`.
- Comments are not visible on the webpage.
- Use comments to improve code readability and organization.
- Avoid storing passwords, API keys, or other sensitive information in comments.


---


## Best Practices

- Write comments only when they add value or explain non-obvious code.
- Keep comments short, clear, and meaningful.
- Use comments to organize different sections of a webpage.
- Remove outdated or unnecessary comments to keep the code clean.
- Use comments to temporarily disable code only during testing or debugging.
- Avoid excessive comments for self-explanatory code.
- Keep comments updated whenever the related code changes.
- Never store passwords, API keys, or sensitive information in HTML comments.


---

## Common Mistakes

### 1. Forgetting to Close a Comment

❌ Incorrect

```html
<!-- This comment is not closed

<h1>Welcome</h1>
```

✅ Correct

```html
<!-- This comment is closed -->

<h1>Welcome</h1>
```

---

### 2. Storing Sensitive Information in Comments

❌ Incorrect

```html
<!-- API Key: abc123xyz -->
<!-- Password: admin123 -->
```

✅ Correct

Never store passwords, API keys, tokens, or other sensitive information in HTML comments because anyone can view the page source.

---

### 3. Overusing Comments

❌ Incorrect

```html
<!-- This is a heading -->
<h1>Welcome</h1>
```

✅ Correct

Use comments only when they explain something that isn't obvious from the code itself.

---

### 4. Leaving Debug Comments in Production

❌ Incorrect

```html
<!-- TODO: Remove this section before deployment -->
```

✅ Correct

Remove temporary debugging or development comments before publishing your website.

---

### 5. Using Comments to Hide Important Content

❌ Incorrect

```html
<!--
<h2>Special Offer</h2>
<p>50% Discount</p>
-->
```

✅ Correct

Use comments only for development purposes. If content should not appear on the webpage, remove it instead of leaving it commented out.


---

## Interview Questions

### Basic Questions

1. What is an HTML comment?
2. What is the syntax for writing an HTML comment?
3. Are HTML comments displayed in the browser?
4. Why are HTML comments used?
5. Can HTML comments span multiple lines?

### Intermediate Questions

6. How can HTML comments help during debugging?
7. Why should sensitive information never be stored in HTML comments?
8. What happens if an HTML comment is not closed properly?
9. When should you remove HTML comments from your code?
10. What are the advantages and disadvantages of using HTML comments?

### Practical Questions

11. Write the syntax for an HTML comment.
12. How would you temporarily disable a paragraph using HTML comments?
13. How do HTML comments improve code maintainability?
14. Explain the difference between visible HTML content and HTML comments.
15. What are some best practices for using HTML comments in a team project?


---


## Practice Exercises

### Exercise 1: Write Your First Comment

Create an HTML document and add:

- A heading
- A paragraph
- A comment above the heading describing the section

---

### Exercise 2: Organize a Webpage

Create a webpage and separate the following sections using comments:

- Header
- Navigation
- Main Content
- Sidebar
- Footer

Example:

```html
<!-- Header -->
<header>
    <h1>My Website</h1>
</header>

<!-- Navigation -->
<nav>
    <a href="#">Home</a>
</nav>
```

---

### Exercise 3: Disable HTML Code

Temporarily comment out a paragraph without deleting it.

```html
<!--
<p>This paragraph is temporarily disabled.</p>
-->
```

---

### Exercise 4: Find the Mistakes

Identify and fix the problems in the following code:

```html
<!-- Website Header

<h1>Welcome</h1>

<!-- Password: admin123 -->
```

---

### Challenge Exercise

Create a simple webpage containing:

- Header
- Main content
- Footer

Use meaningful comments to organize each section and ensure no unnecessary or sensitive information is included in the comments.


---


## Related Topics

Continue learning with the following topics:

### Previous Topics

- [HTML Basics](01-html-basics.md)
- [HTML Page Structure](02-page-structure.md)

### Next Topics

- [HTML Tags](04-tags.md)
- [HTML Elements](05-elements.md)
- [HTML Attributes](06-attributes.md)
- [HTML ID and Classes](07-id-classes.md)
- [Inline and Block Elements](08-inline-block-elements.md)