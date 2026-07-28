# HTML Elements

## Introduction

HTML elements are the fundamental building blocks of an HTML document. They define the structure and content of a webpage, such as headings, paragraphs, links, images, tables, forms, and more.

An HTML element is created using HTML tags. While tags mark the beginning and end of an element, the element itself includes the opening tag, the content, and the closing tag (when applicable).

Understanding HTML elements is essential because every webpage is made up of different elements working together to display information in a structured and meaningful way.


---


## What is an HTML Element?

An HTML element is a complete unit of an HTML document. It is created using HTML tags and usually consists of:

- An opening tag
- The content
- A closing tag

### Syntax

```html
<tagname>Content</tagname>
```

### Example

```html
<p>This is a paragraph.</p>
```

In the example above:

- `<p>` is the opening tag.
- `This is a paragraph.` is the content.
- `</p>` is the closing tag.

Together, they form a complete **HTML element**.

Some HTML elements do not contain content and therefore do not require a closing tag. These are called **empty (void) elements**, which will be discussed later in this document.


---


## Structure of an HTML Element

A typical HTML element consists of three main parts:

1. Opening Tag
2. Content
3. Closing Tag

### Structure

```html
<tagname>Content</tagname>
```

### Example

```html
<h1>Welcome to HTML</h1>
```

Let's break it down:

| Part | Description |
|------|-------------|
| `<h1>` | Opening tag that marks the beginning of the element. |
| `Welcome to HTML` | The content displayed on the webpage. |
| `</h1>` | Closing tag that marks the end of the element. |

Together, these three parts form a complete HTML element.

### Another Example

```html
<a href="https://example.com">Visit Website</a>
```

Here:

- `<a href="https://example.com">` is the opening tag.
- `Visit Website` is the content.
- `</a>` is the closing tag.

The opening tag can also contain **attributes**, which provide additional information about the element. Attributes will be covered in a later topic.