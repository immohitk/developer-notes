# CSS Media Queries

## Table of Contents

- Introduction
- What Are Media Queries?
- Why Are Media Queries Important?
- Media Query Syntax
- Media Types
- Media Features
- Width and Height
- min-width
- max-width
- Combining Conditions
- Logical Operators
- Orientation
- Responsive Breakpoints
- Mobile-First Approach
- Desktop-First Approach
- Common Responsive Patterns
- Practical Examples
- Key Takeaways
- References
- Quick Revision
- Best Practices
- Common Mistakes
- Interview Questions
- Practice Exercises
- Related Topics

---

# Introduction

CSS Media Queries are an important part of responsive web design.

They allow CSS styles to be applied conditionally based on characteristics of the device, viewport, or browsing environment.

For example, a webpage can use one layout on a large screen and a different layout on a smaller screen.

```css
@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}