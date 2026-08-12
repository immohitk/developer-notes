## Table of Contents

1. [Introduction](#introduction)
2. [What Are Media Queries?](#what-are-media-queries)
3. [Why Are Media Queries Important?](#why-are-media-queries-important)
4. [Media Query Syntax](#media-query-syntax)
5. [Media Types](#media-types)
6. [Media Features](#media-features)
7. [Width and Height](#width-and-height)
8. [min-width](#min-width)
9. [max-width](#max-width)
10. [Combining Conditions](#combining-conditions)
11. [Logical Operators](#logical-operators)
12. [Orientation](#orientation)
13. [Responsive Breakpoints](#responsive-breakpoints)
14. [Mobile-First Approach](#mobile-first-approach)
15. [Desktop-First Approach](#desktop-first-approach)
16. [Common Responsive Patterns](#common-responsive-patterns)
17. [Practical Examples](#practical-examples)
18. [Key Takeaways](#key-takeaways)
19. [References](#references)
20. [Quick Revision](#quick-revision)
21. [Best Practices](#best-practices)
22. [Common Mistakes](#common-mistakes)
23. [Interview Questions](#interview-questions)
24. [Practice Exercises](#practice-exercises)
25. [Related Topics](#related-topics)

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

