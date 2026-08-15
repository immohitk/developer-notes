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

---

## What Are CSS Animations?

CSS animations allow an element's CSS properties to change automatically over time according to a sequence of defined stages.

Unlike a transition, an animation does not require a state change such as `:hover` to start. Once an animation is applied to an element, it can run automatically.

A CSS animation is mainly created using two parts:

```text
@keyframes
    ↓
Defines the stages of the animation

animation
    ↓
Applies and controls the animation
```

### Basic Example

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

Here:

```text
move
    ↓
Animation name

2s
    ↓
Animation duration

ease
    ↓
Animation timing function
```

The `@keyframes` rule defines how the `.box` changes from its starting position to its ending position.

### How CSS Animations Work

A CSS animation generally follows this process:

```text
1. Define animation stages
        ↓
2. Give the animation a name
        ↓
3. Apply the animation to an element
        ↓
4. Browser runs the animation
```

For example:

```css
.box {
    animation: slide 1s ease;
}

@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The browser starts the `slide` animation when the `.box` is rendered.

### Animations with Multiple Stages

CSS animations can contain more than just a starting and ending stage.

Percentage values can be used to define multiple stages:

```css
.box {
    animation: move 3s ease;
}

@keyframes move {
    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(100px);
    }

    100% {
        transform: translateX(200px);
    }
}
```

The animation now has three stages:

```text
0%
 ↓
Starting position

50%
 ↓
Middle position

100%
 ↓
Ending position
```

### Animations Can Run Automatically

A transition normally requires a property value to change between states.

For example:

```css
.button {
    transition: transform 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

The transition runs when the hover state changes.

An animation can run automatically:

```css
.box {
    animation: spin 2s linear infinite;
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

No `:hover` state is required.

### Animating Different CSS Properties

Animations can change many CSS properties.

For example, a color animation:

```css
.box {
    animation: colorChange 2s ease;
}

@keyframes colorChange {
    from {
        background-color: steelblue;
    }

    to {
        background-color: darkblue;
    }
}
```

An opacity animation:

```css
.box {
    animation: fade 1s ease;
}

@keyframes fade {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

A transform animation:

```css
.box {
    animation: scaleUp 1s ease;
}

@keyframes scaleUp {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(1.2);
    }
}
```

### CSS Animations vs CSS Transitions

The main difference is how they are triggered and defined.

CSS transition:

```text
State A
   ↓
Transition
   ↓
State B
```

CSS animation:

```text
@keyframes
   ↓
Stage 1
   ↓
Stage 2
   ↓
Stage 3
   ↓
Animation complete
```

For example:

```css
/* Transition */

.button {
    transition: transform 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

```css
/* Animation */

.box {
    animation: bounce 1s ease;
}

@keyframes bounce {
    0% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-30px);
    }

    100% {
        transform: translateY(0);
    }
}
```

### Repeating Animations

Animations can repeat using `animation-iteration-count`.

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

The `infinite` value makes the animation repeat continuously.

### Common Uses of CSS Animations

CSS animations are commonly used for:

- Loading indicators
- Spinners
- Entrance effects
- Attention effects
- Moving elements
- Fading effects
- Rotations
- Repeated effects
- Decorative effects
- Interactive components

For example, a loading spinner:

```css
.loader {
    width: 40px;
    height: 40px;
    border: 4px solid lightgray;
    border-top-color: steelblue;
    border-radius: 50%;

    animation: spin 1s linear infinite;
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}
```

> 💡 **Tip:** Use CSS animations when an effect needs multiple stages, automatic playback, or repetition. Use transitions when you mainly need a smooth change between states.

> 💡 **Remember:** CSS animations are built using `@keyframes` and the `animation` properties. `@keyframes` defines **what happens**, while `animation` controls **how it runs**.