## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Transitions?](#what-are-css-transitions)
- [Why Are CSS Transitions Important?](#why-are-css-transitions-important)
- [Transition Syntax](#transition-syntax)
- [Transition Property](#transition-property)
- [Transition Duration](#transition-duration)
- [Transition Timing Function](#transition-timing-function)
- [Transition Delay](#transition-delay)
- [Transition Shorthand](#transition-shorthand)
- [Multiple Transitions](#multiple-transitions)
- [Transitions with Hover](#transitions-with-hover)
- [Transitions with Transform](#transitions-with-transform)
- [Transitions with Colors](#transitions-with-colors)
- [Transitions with Size](#transitions-with-size)
- [Transitions with Position](#transitions-with-position)
- [Practical Examples](#practical-examples)
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

CSS transitions allow CSS property values to change smoothly over a specified period of time.

Normally, when a CSS property changes, the browser applies the new value immediately. A transition makes the change gradual, creating a smoother visual effect.

For example, without a transition:

```css
button {
    background-color: steelblue;
}

button:hover {
    background-color: darkblue;
}
```

The button changes from `steelblue` to `darkblue` immediately when the user hovers over it.

With a transition:

```css
button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: darkblue;
}
```

The background color now changes gradually over `0.3` seconds.

CSS transitions are commonly used for interactive effects such as:

- Hover effects
- Button interactions
- Links
- Cards
- Navigation menus
- Image effects
- Color changes
- Size changes
- Position changes
- Transform effects

> 💡 **Tip:** A transition does not create a new state by itself. It controls how smoothly a property changes from one value to another.

> 💡 **Remember:** CSS transitions are mainly used to make changes between CSS states appear smooth rather than immediate.

---

## What Are CSS Transitions?

CSS transitions are a CSS feature that allows a property to change smoothly from one value to another over a specified period of time.

Without a transition, a CSS property usually changes immediately when a new state is applied.

For example:

```css
.button {
    background-color: steelblue;
}

.button:hover {
    background-color: darkblue;
}
```

The background color changes immediately when the user hovers over the button.

By adding a transition:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The browser gradually changes the background color from `steelblue` to `darkblue` over `0.3` seconds.

### How CSS Transitions Work

A transition generally involves three things:

```text
Initial value
     ↓
Transition
     ↓
New value
```

For example:

```css
.box {
    width: 100px;
    transition: width 0.5s ease;
}

.box:hover {
    width: 200px;
}
```

The element starts with a width of `100px`.

When the user hovers over it, the width changes to `200px`.

The transition makes this change happen gradually over `0.5` seconds.

### Transitions and States

Transitions are commonly used when an element changes between different states.

For example:

```css
button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: darkblue;
}
```

Here:

```text
Normal State
    ↓
steelblue
    ↓
Hover
    ↓
darkblue
```

The transition controls how the browser moves from the normal state to the hover state.

### Common Properties Used with Transitions

Transitions can be used with many CSS properties, including:

- `background-color`
- `color`
- `opacity`
- `width`
- `height`
- `margin`
- `padding`
- `border-color`
- `transform`

For example:

```css
.box {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.box:hover {
    opacity: 0.5;
}
```

### Transition Does Not Create the Change

A transition does not define the new property value.

The property value is changed by another rule, while the transition controls how that change happens.

For example:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.05);
}
```

Here:

```text
transform: scale(1.05)
        ↓
Creates the change

transition: transform 0.3s ease
        ↓
Controls how the change happens
```

> 💡 **Remember:** A CSS transition controls the smoothness and timing of a change; it does not create the changed state itself.

> 💡 **Tip:** Transitions are especially useful for interactive states such as `:hover`, `:focus`, and `:active`.