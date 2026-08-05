## Table of Contents

- [Introduction](#introduction)
- [What is the CSS Box Model?](#what-is-the-css-box-model)
- [Content Area](#content-area)
- [Padding](#padding)
- [Border](#border)
- [Margin](#margin)
- [Width and Height](#width-and-height)
- [Box Sizing](#box-sizing)
- [Content Box vs Border Box](#content-box-vs-border-box)
- [Visual Box Model Diagram](#visual-box-model-diagram)
- [How the Browser Calculates Element Size](#how-the-browser-calculates-element-size)
- [Margin Collapse](#margin-collapse)
- [Common Layout Examples](#common-layout-examples)
- [Which `box-sizing` Should You Use?](#which-box-sizing-should-you-use)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


## Introduction

Every HTML element on a webpage is treated as a **rectangular box** by the browser.

Whether you're styling a button, image, heading, paragraph, or an entire webpage, each element follows the same fundamental layout model known as the **CSS Box Model**.

The Box Model defines how the browser calculates the size of an element and how much space it occupies on the page. It consists of four main parts:

- **Content** – The actual content of the element.
- **Padding** – Space between the content and the border.
- **Border** – A line surrounding the padding and content.
- **Margin** – Space outside the border that separates elements from one another.

Understanding the Box Model is essential because almost every CSS layout depends on it. Incorrect spacing, unexpected element sizes, and many common layout issues can often be traced back to a misunderstanding of the Box Model.

In this chapter, you'll learn how each part of the Box Model works, how browsers calculate element dimensions, and how to use properties such as `box-sizing` to build predictable, maintainable layouts.

> 💡 **Pro Tip:** If an element doesn't look the size or position you expected, inspect its Box Model in your browser's Developer Tools. It's one of the fastest ways to identify layout and spacing issues.