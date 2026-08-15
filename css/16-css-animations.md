## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Animations?](#what-are-css-animations)
- [Why Are CSS Animations Important?](#why-are-css-animations-important)
- [Animation Syntax](#animation-syntax)
- [@keyframes Rule](#keyframes-rule)
- [Animation Name](#animation-name)
- [Animation Duration](#animation-duration)
- [Animation Timing Function](#animation-timing-function)
- [Animation Delay](#animation-delay)
- [Animation Iteration Count](#animation-iteration-count)
- [Animation Direction](#animation-direction)
- [Animation Fill Mode](#animation-fill-mode)
- [Animation Play State](#animation-play-state)
- [Animation Shorthand](#animation-shorthand)
- [Multiple Animations](#multiple-animations)
- [Animations with Transform](#animations-with-transform)
- [Animations with Colors](#animations-with-colors)
- [Animations with Opacity](#animations-with-opacity)
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

CSS animations allow you to create dynamic visual effects by changing CSS properties over time.

Unlike CSS transitions, which generally describe a change between two states, CSS animations can define multiple stages of a visual effect using the `@keyframes` rule.

For example:

```css
.box {
    animation: move 2s ease;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

In this example:

- `@keyframes` defines the animation stages.
- `move` is the animation name.
- `2s` defines the animation duration.
- `ease` defines the timing function.
- `transform` defines what changes during the animation.

### CSS Animations vs CSS Transitions

CSS transitions are generally used when an element changes between states.

```text
Normal → Hover
Normal → Focus
```

CSS animations can run through a defined sequence of stages.

```text
Start → Middle → End
```

For example:

```css
@keyframes colorChange {
    0% {
        background-color: steelblue;
    }

    50% {
        background-color: purple;
    }

    100% {
        background-color: darkblue;
    }
}
```

This animation contains three stages.

### Why Use CSS Animations?

CSS animations can be used to create effects such as:

- Moving elements
- Fading elements
- Rotating elements
- Scaling elements
- Changing colors
- Loading indicators
- Attention effects
- Entrance and exit effects
- Repeated visual effects

For example:

```css
.loader {
    animation: spin 1s linear infinite;
}

@keyframes spin {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
```

The animation continuously rotates the element.

### Basic Animation Structure

A CSS animation usually consists of two main parts:

```text
@keyframes
    ↓
Defines what happens

animation property
    ↓
Defines how the animation runs
```

For example:

```css
.box {
    animation: slide 2s ease;
}

@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

The `@keyframes` rule defines the animation, while the `animation` property applies it to the element.

> 💡 **Tip:** CSS animations are useful when you need a sequence of visual changes that can run automatically or repeat multiple times.

> 💡 **Remember:** `@keyframes` defines the animation stages, while the `animation` property controls how those stages are played.