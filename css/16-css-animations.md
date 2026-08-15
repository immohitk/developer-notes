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

---

## Why Are CSS Animations Important?

CSS animations are important because they allow websites to create dynamic visual effects without requiring JavaScript for many common animation tasks.

They can make interfaces more engaging, provide visual feedback, communicate changes, and draw attention to important elements.

### 1. Improve User Experience

Animations can help users understand what is happening on a page.

For example, an element can smoothly appear when content is loaded:

```css
.message {
    animation: fadeIn 0.5s ease;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

The gradual appearance makes the change easier to notice.

### 2. Provide Visual Feedback

Animations can communicate that an action has occurred.

For example:

```css
.button {
    animation: press 0.2s ease;
}

@keyframes press {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(0.95);
    }
}
```

Small visual changes can help users understand interactions.

### 3. Create Loading Indicators

Animations are commonly used to show that a process is running.

For example:

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

The repeated rotation indicates that something is still loading.

### 4. Create Attention Effects

Animations can be used to draw attention to an important element.

For example:

```css
.notification {
    animation: pulse 1s ease-in-out infinite;
}

@keyframes pulse {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }

    100% {
        transform: scale(1);
    }
}
```

The repeated scaling makes the notification more noticeable.

### 5. Create Entrance Effects

Animations can make elements appear smoothly when they enter a page or section.

```css
.card {
    animation: slideIn 0.6s ease;
}

@keyframes slideIn {
    from {
        transform: translateY(30px);
        opacity: 0;
    }

    to {
        transform: translateY(0);
        opacity: 1;
    }
}
```

The card moves upward while becoming visible.

### 6. Create Repeating Effects

CSS animations can repeat automatically.

```css
.loader {
    animation: spin 1s linear infinite;
}
```

The `infinite` value makes the animation continue repeating.

This is useful for:

- Loading indicators
- Decorative effects
- Status indicators
- Repeating visual feedback

### 7. Create Multi-Stage Effects

Unlike a simple two-state transition, animations can contain multiple stages.

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

This allows an animation to have different values at different points in time.

### 8. Reduce the Need for JavaScript

Many simple visual effects can be created entirely with CSS.

For example:

```css
.spinner {
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

No JavaScript is required to continuously rotate the spinner.

JavaScript may still be useful when animation behavior needs to depend on application logic or user data.

### 9. Improve Visual Communication

Animation can help communicate relationships and changes between interface states.

For example, an element can smoothly move into a new position:

```css
.panel {
    animation: enter 0.4s ease-out;
}

@keyframes enter {
    from {
        transform: translateX(-100%);
    }

    to {
        transform: translateX(0);
    }
}
```

The movement can help users understand where the panel came from.

### 10. Create More Engaging Interfaces

Well-designed animations can make interfaces feel more polished and responsive.

Common examples include:

- Animated buttons
- Loading indicators
- Notification effects
- Image effects
- Menu transitions
- Entrance effects
- Progress indicators
- Attention effects

### Animation Should Have a Purpose

Animations should support the interface rather than simply add movement.

Good use:

```text
User action
    ↓
Visual feedback
    ↓
User understands the result
```

Poor use:

```text
Animation
    ↓
Unnecessary movement
    ↓
Distraction
```

### CSS Animations vs Transitions

CSS transitions are commonly used for changes between states:

```text
Normal → Hover
Normal → Focus
```

CSS animations are useful when you need:

```text
Multiple stages
Automatic playback
Repeated effects
Timed sequences
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

### Accessibility Considerations

Animations should also consider users who prefer reduced motion.

The `prefers-reduced-motion` media feature can be used to reduce or disable animations.

```css
.loader {
    animation: spin 1s linear infinite;
}

@media (prefers-reduced-motion: reduce) {
    .loader {
        animation: none;
    }
}
```

This can make animated interfaces more comfortable for users who have requested reduced motion.

> 💡 **Tip:** Use animations when they communicate something useful, improve feedback, or support the structure of the interface.

> 💡 **Remember:** Good animation has a purpose. It should improve understanding and interaction rather than distract the user.

---

## Animation Syntax

The `animation` property is used to apply a CSS animation to an element.

A CSS animation generally requires:

1. An animation name.
2. A set of `@keyframes` that defines what happens during the animation.

### Basic Syntax

The basic syntax is:

```css
selector {
    animation: animation-name duration;
}
```

For example:

```css
.box {
    animation: move 2s;
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
```

The animation named `move` must be defined using `@keyframes`.

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

### Complete Animation Syntax

The `animation` shorthand can include several values:

```css
selector {
    animation: name duration timing-function delay iteration-count direction fill-mode play-state;
}
```

For example:

```css
.box {
    animation: move 2s ease 0s 1 normal forwards running;
}
```

The values represent:

```text
move     → Animation name
2s       → Duration
ease     → Timing function
0s       → Delay
1        → Iteration count
normal   → Direction
forwards → Fill mode
running  → Play state
```

### Using Individual Animation Properties

Instead of using the shorthand, each animation property can be written separately.

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-timing-function: ease;
    animation-delay: 0s;
    animation-iteration-count: 1;
    animation-direction: normal;
    animation-fill-mode: forwards;
    animation-play-state: running;
}
```

This is more verbose but can make individual settings easier to understand.

### Basic Example

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

The `.box` element runs the `slide` animation for one second using the `ease` timing function.

### Animation Name

The first value identifies the `@keyframes` animation.

```css
.box {
    animation: slide 2s;
}
```

The corresponding keyframes are:

```css
@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

The names must match:

```text
animation: slide
           ↓
@keyframes slide
```

### Animation Duration

The duration specifies how long one animation cycle takes.

```css
.box {
    animation: move 2s;
}
```

The animation takes `2` seconds to complete one cycle.

It can also be written using milliseconds:

```css
.box {
    animation: move 500ms;
}
```

### Timing Function

The timing function controls the speed pattern of the animation.

```css
.box {
    animation: move 2s ease-in-out;
}
```

Common values include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

### Delay

A delay specifies how long the browser waits before starting the animation.

```css
.box {
    animation: move 2s ease 0.5s;
}
```

Here:

```text
2s   → Duration
0.5s → Delay
```

### Iteration Count

The iteration count specifies how many times the animation should run.

```css
.box {
    animation: move 2s ease 0s 3;
}
```

The animation runs three times.

To repeat continuously:

```css
.box {
    animation: move 2s ease infinite;
}
```

### Direction

The animation direction controls the direction in which animation cycles are played.

```css
.box {
    animation: move 2s ease infinite alternate;
}
```

The `alternate` value causes the animation to play forward and then backward on successive cycles.

### Fill Mode

The fill mode controls how an element is styled before and after the animation.

For example:

```css
.box {
    animation: move 2s ease forwards;
}
```

The `forwards` value causes the element to retain the styles from the final keyframe after the animation finishes.

### Play State

The play state controls whether an animation is running or paused.

```css
.box {
    animation: move 2s ease infinite;
    animation-play-state: paused;
}
```

The animation can be started again by changing the value:

```css
.box:hover {
    animation-play-state: running;
}
```

### Shorthand Example

A more complete example can combine several animation settings:

```css
.box {
    animation: move 2s ease-in-out 0.5s infinite alternate;
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
move       → Animation name
2s         → Duration
ease-in-out → Timing function
0.5s       → Delay
infinite   → Iteration count
alternate  → Direction
```

### Important Point

The `animation` property controls how an animation is played, while `@keyframes` defines the actual stages.

```text
@keyframes
    ↓
Defines the changes

animation
    ↓
Controls the playback
```

> 💡 **Tip:** Start with the basic syntax `animation: name duration;` and add other values only when the animation requires additional control.

> 💡 **Remember:** The animation name connects the `animation` property to the corresponding `@keyframes` rule.

---

## @keyframes Rule

The `@keyframes` rule defines the stages of a CSS animation.

It specifies how CSS properties should change at different points during the animation.

The `animation` property controls how the animation runs, while `@keyframes` defines what happens during the animation.

### Basic Syntax

The basic syntax is:

```css
@keyframes animation-name {
    from {
        property: value;
    }

    to {
        property: value;
    }
}
```

For example:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

The animation starts at the `from` state and ends at the `to` state.

### Applying the Keyframes

The `@keyframes` rule only defines the animation. It must be applied to an element using the `animation` property.

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
@keyframes move
       ↓
Defines the animation

animation: move
       ↓
Applies the animation
```

### Using `from` and `to`

The `from` and `to` keywords represent the beginning and ending states.

```css
@keyframes fade {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

This creates a fade-in effect.

### Using Percentages

Instead of `from` and `to`, percentage values can be used to define specific stages.

```css
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

The percentages represent the progress of the animation:

```text
0%
 ↓
Beginning

50%
 ↓
Middle

100%
 ↓
End
```

### Multiple Keyframes

An animation can contain multiple stages.

```css
@keyframes bounce {
    0% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-50px);
    }

    100% {
        transform: translateY(0);
    }
}
```

This creates a simple bouncing effect.

### Animating Multiple Properties

Multiple CSS properties can be changed inside the same keyframe.

```css
@keyframes fadeMove {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The element simultaneously:

- Changes its opacity.
- Moves vertically.

### Changing Colors

Keyframes can animate color properties.

```css
@keyframes colorChange {
    from {
        background-color: steelblue;
    }

    to {
        background-color: darkblue;
    }
}
```

The animation can then be applied:

```css
.box {
    animation: colorChange 2s ease;
}
```

### Rotating an Element

The `transform` property can be used to create rotation animations.

```css
@keyframes rotate {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
```

Apply it with:

```css
.icon {
    animation: rotate 2s linear;
}
```

### Scaling an Element

Keyframes can also change the scale of an element.

```css
@keyframes grow {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(1.2);
    }
}
```

Apply the animation:

```css
.box {
    animation: grow 1s ease;
}
```

### Combining Different Effects

Several properties can be changed at different stages.

```css
@keyframes entrance {
    0% {
        opacity: 0;
        transform: translateY(30px) scale(0.95);
    }

    100% {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
}
```

This creates an entrance effect by combining:

```text
Opacity
   +
Movement
   +
Scaling
```

### Keyframe Names

The name after `@keyframes` identifies the animation.

```css
@keyframes slideIn {
    /* animation stages */
}
```

The same name is then used with the `animation` property:

```css
.box {
    animation: slideIn 1s ease;
}
```

The names must correspond:

```text
@keyframes slideIn
        ↕
animation: slideIn
```

### Keyframes Do Not Start an Animation by Themselves

Defining keyframes does not automatically apply them to an element.

For example:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

This only defines the animation.

An element must use:

```css
.box {
    animation: move 1s ease;
}
```

### Practical Example

```html
<div class="box">Animate Me</div>
```

```css
.box {
    animation: slideIn 1s ease;
}

@keyframes slideIn {
    0% {
        opacity: 0;
        transform: translateX(-50px);
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}
```

When the page loads, the box starts with reduced opacity and a shifted position, then smoothly moves into its final position while becoming visible.

### Important Relationship

```text
@keyframes
    ↓
Defines animation stages

animation-name
    ↓
Identifies the keyframes

animation-duration
    ↓
Controls how long the animation takes
```

> 💡 **Tip:** Use percentage keyframes when an animation needs more than a simple beginning and ending state.

> 💡 **Remember:** `@keyframes` defines **what changes during an animation**, while the `animation` property determines **how that animation is played**.

---

## Animation Name

The `animation-name` property specifies the name of the `@keyframes` rule that should be applied to an element.

The name connects the element with the animation stages defined using `@keyframes`.

### Basic Syntax

```css
selector {
    animation-name: animation-name;
}
```

For example:

```css
.box {
    animation-name: move;
}
```

The corresponding `@keyframes` rule is:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

The name `move` connects the two declarations.

```text
animation-name: move
        ↓
@keyframes move
```

### Animation Name with Duration

The animation name alone does not specify how long the animation should run.

```css
.box {
    animation-name: move;
    animation-duration: 2s;
}
```

Here:

```text
animation-name
    ↓
Which animation?

animation-duration
    ↓
How long does it run?
```

### Using the Shorthand

The same animation can be written using the `animation` shorthand.

```css
.box {
    animation: move 2s ease;
}
```

This combines the animation name with other animation properties.

### Naming an Animation

Choose a descriptive name that indicates what the animation does.

Good examples:

```text
fadeIn
slideIn
slideOut
rotate
bounce
scaleUp
fadeOut
```

For example:

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Then:

```css
.box {
    animation-name: fadeIn;
    animation-duration: 0.5s;
}
```

### Animation Name Must Match the Keyframes

The value of `animation-name` should correspond to the intended `@keyframes` name.

Correct:

```css
.box {
    animation-name: slideIn;
}

@keyframes slideIn {
    from {
        transform: translateX(-50px);
    }

    to {
        transform: translateX(0);
    }
}
```

If the names do not match, the intended keyframes will not be applied.

For example:

```css
.box {
    animation-name: slideIn;
}

@keyframes slide {
    from {
        transform: translateX(-50px);
    }

    to {
        transform: translateX(0);
    }
}
```

Here, `animation-name` refers to `slideIn`, but the defined keyframes are named `slide`.

### No Animation Name

The `animation-name` property can be set to `none`.

```css
.box {
    animation-name: none;
}
```

This means that no keyframe animation is applied.

### Multiple Animation Names

Multiple animations can be assigned to the same element by separating their names with commas.

```css
.box {
    animation-name: move, fade;
}
```

The corresponding keyframes are:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
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

When using multiple animations, the related animation properties can also be provided as comma-separated values.

```css
.box {
    animation-name: move, fade;
    animation-duration: 1s, 2s;
}
```

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    animation-name: slideIn;
    animation-duration: 1s;
    animation-timing-function: ease-out;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

The `animation-name` property tells the browser to use the `slideIn` keyframes.

> 💡 **Tip:** Use descriptive animation names such as `fadeIn`, `slideIn`, or `rotate` so the purpose of the animation is easy to understand.

> 💡 **Remember:** `animation-name` connects an element to a specific `@keyframes` rule. The names must correspond for the intended animation to run.

---

## Animation Duration

The `animation-duration` property specifies how long one cycle of a CSS animation should take to complete.

It determines the amount of time required for the animation to move from its starting keyframe to its ending keyframe.

### Basic Syntax

```css
selector {
    animation-duration: time;
}
```

For example:

```css
.box {
    animation-duration: 2s;
}
```

The animation takes `2` seconds to complete one cycle.

### Using Seconds

Seconds (`s`) are commonly used for animation durations.

```css
.box {
    animation-duration: 2s;
}
```

Other examples:

```css
animation-duration: 0.5s;
animation-duration: 1s;
animation-duration: 3s;
```

### Using Milliseconds

Milliseconds (`ms`) can also be used.

```css
.box {
    animation-duration: 500ms;
}
```

Since:

```text
1s = 1000ms
```

the following values are equivalent:

```css
animation-duration: 1s;
```

```css
animation-duration: 1000ms;
```

### Duration with `@keyframes`

The duration controls how quickly the keyframes are played.

```css
.box {
    animation-name: move;
    animation-duration: 2s;
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

The complete movement takes `2` seconds.

### Short Duration

A short duration makes the animation happen quickly.

```css
.box {
    animation-duration: 0.3s;
}
```

This can be useful for small interface effects.

### Long Duration

A longer duration makes the animation happen more slowly.

```css
.box {
    animation-duration: 3s;
}
```

The same keyframes now take three seconds to complete.

### Comparing Durations

The same animation can feel very different depending on its duration.

```text
0.2s
 ↓
Very fast

0.5s
 ↓
Fast

1s
 ↓
Moderate

2s
 ↓
Slow

5s
 ↓
Very slow
```

These are only general examples. The appropriate duration depends on the type of animation and the interface.

### Duration and Repeated Animations

When an animation repeats, `animation-duration` determines how long each cycle takes.

```css
.loader {
    animation-name: spin;
    animation-duration: 1s;
    animation-iteration-count: infinite;
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

Here, each complete rotation takes `1` second.

### Duration with the Shorthand

The duration can also be specified using the `animation` shorthand.

```css
.box {
    animation: move 2s ease;
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
Timing function
```

### Multiple Animations

When multiple animations are used, each animation can have its own duration.

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
}
```

Here:

```text
move → 2 seconds
fade → 1 second
```

The values correspond by position.

### Duration Must Be Appropriate

The duration should match the purpose of the animation.

For example, a small interface feedback effect might use:

```css
.button {
    animation-duration: 0.2s;
}
```

A larger entrance effect might use:

```css
.card {
    animation-duration: 0.6s;
}
```

A continuously rotating loading indicator might use:

```css
.loader {
    animation-duration: 1s;
}
```

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    animation-name: slideIn;
    animation-duration: 1s;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

The `slideIn` animation takes one second to complete.

> 💡 **Tip:** Choose a duration based on how much visual change occurs. Small effects generally need less time, while larger effects may need more time.

> 💡 **Remember:** `animation-duration` controls **how long one animation cycle takes**. It does not determine how many times the animation repeats.

---

## Animation Timing Function

The `animation-timing-function` property controls the speed pattern of a CSS animation during its execution.

It determines how quickly or slowly the animation progresses between its keyframes.

### Basic Syntax

```css
selector {
    animation-timing-function: value;
}
```

For example:

```css
.box {
    animation-timing-function: ease;
}
```

### Common Timing Functions

CSS provides several commonly used timing functions:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

### `ease`

The `ease` value starts relatively slowly, speeds up, and then slows down toward the end.

```css
.box {
    animation: move 2s ease;
}
```

It is a common general-purpose timing function.

### `linear`

The `linear` value keeps the animation moving at a constant rate.

```css
.box {
    animation: move 2s linear;
}
```

There is no acceleration or deceleration.

This is particularly useful for continuously rotating elements such as loading indicators.

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

### `ease-in`

The `ease-in` value starts slowly and becomes faster toward the end.

```css
.box {
    animation: move 2s ease-in;
}
```

### `ease-out`

The `ease-out` value starts quickly and slows down toward the end.

```css
.box {
    animation: move 2s ease-out;
}
```

This can work well for elements entering or settling into their final position.

### `ease-in-out`

The `ease-in-out` value starts slowly, becomes faster in the middle, and slows down again toward the end.

```css
.box {
    animation: move 2s ease-in-out;
}
```

### Comparing Common Timing Functions

```text
ease
    ↓
Slow → Fast → Slow

linear
    ↓
Constant speed

ease-in
    ↓
Slow → Fast

ease-out
    ↓
Fast → Slow

ease-in-out
    ↓
Slow → Fast → Slow
```

### Timing Function with `@keyframes`

The timing function can be applied to the entire animation.

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-timing-function: ease-out;
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

### Timing Function with Shorthand

The timing function can also be included in the `animation` shorthand.

```css
.box {
    animation: move 2s ease-out;
}
```

Here:

```text
move
    ↓
Animation name

2s
    ↓
Duration

ease-out
    ↓
Timing function
```

### Timing Functions and Multiple Animations

Different animations can have different timing functions.

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
    animation-timing-function: ease-out, linear;
}
```

Here:

```text
move → ease-out
fade → linear
```

The values correspond by position.

### Custom Timing Functions

CSS also supports custom timing functions using `cubic-bezier()`.

```css
.box {
    animation-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
```

This provides more control over the acceleration and deceleration of the animation.

### `steps()` Timing Function

The `steps()` function creates a stepped animation rather than a continuously smooth one.

```css
.box {
    animation-timing-function: steps(4);
}
```

This can be useful for effects that should change in distinct steps.

### Choosing a Timing Function

The timing function should match the type of effect.

```text
Continuous rotation
    ↓
linear

Element entering
    ↓
ease-out

Element leaving
    ↓
ease-in

General movement
    ↓
ease

Smooth movement in both directions
    ↓
ease-in-out
```

These are useful starting points rather than strict rules.

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    animation:
        slideIn 1s ease-out;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

The animation starts quickly and gradually slows as the element reaches its final position.

### Important Point

The timing function does not define the animation's stages.

The `@keyframes` rule defines the stages:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

The timing function controls how the animation progresses between those stages:

```css
animation-timing-function: ease-out;
```

> 💡 **Tip:** Use `linear` for constant-speed effects such as spinners and consider `ease-out` for elements that should settle naturally into their final position.

> 💡 **Remember:** `animation-timing-function` controls **the speed pattern of an animation**, not the animation's duration or keyframe values.

---

## Animation Delay

The `animation-delay` property specifies how long the browser should wait before starting a CSS animation.

It is useful when an animation should begin after a short pause or when several elements should start their animations at different times.

### Basic Syntax

```css
selector {
    animation-delay: time;
}
```

For example:

```css
.box {
    animation-delay: 1s;
}
```

The animation waits for `1` second before starting.

### Using Seconds

Seconds (`s`) are commonly used for animation delays.

```css
.box {
    animation-delay: 0.5s;
}
```

Other examples:

```css
animation-delay: 0s;
animation-delay: 1s;
animation-delay: 2s;
```

### Using Milliseconds

Milliseconds (`ms`) can also be used.

```css
.box {
    animation-delay: 500ms;
}
```

Since:

```text
1s = 1000ms
```

these values represent the same delay:

```css
animation-delay: 1s;
```

```css
animation-delay: 1000ms;
```

### Animation Delay with Keyframes

The delay controls when the animation begins, while `@keyframes` defines what happens during the animation.

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-delay: 1s;
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
1s
 ↓
Wait before starting

2s
 ↓
Time taken by the animation
```

### Delay Does Not Change the Duration

Consider:

```css
.box {
    animation-duration: 2s;
    animation-delay: 1s;
}
```

The animation still takes `2s` to complete.

The browser simply waits `1s` before starting it.

```text
Page loads
    ↓
Wait 1 second
    ↓
Animation starts
    ↓
Animation runs for 2 seconds
```

### Zero Delay

The default delay is effectively zero.

```css
.box {
    animation-delay: 0s;
}
```

The animation starts without an intentional delay.

### Negative Delay

CSS also allows a negative animation delay.

```css
.box {
    animation-delay: -1s;
}
```

A negative delay causes the animation to begin as if it had already been running for that amount of time.

For example:

```css
.box {
    animation: move 4s linear -2s;
}
```

The animation begins at a point corresponding to approximately two seconds into its timeline rather than waiting for two seconds.

This can be useful when multiple animated elements need to appear at different points in the same animation.

### Delay with the Shorthand

The delay can be included in the `animation` shorthand.

```css
.box {
    animation: move 2s ease 1s;
}
```

Here:

```text
move
 ↓
Animation name

2s
 ↓
Duration

ease
 ↓
Timing function

1s
 ↓
Delay
```

### Multiple Animations

Different animations can have different delays.

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
    animation-delay: 0s, 0.5s;
}
```

Here:

```text
move → starts immediately
fade → starts after 0.5s
```

The values correspond by position.

### Staggered Animations

Animation delays can be used to create a staggered effect.

For example:

```css
.item:nth-child(1) {
    animation-delay: 0s;
}

.item:nth-child(2) {
    animation-delay: 0.2s;
}

.item:nth-child(3) {
    animation-delay: 0.4s;
}
```

Each item starts slightly after the previous one.

This can create effects such as:

```text
Item 1
   ↓
Item 2
   ↓
Item 3
```

### Practical Example

```html
<div class="container">
    <div class="item">One</div>
    <div class="item">Two</div>
    <div class="item">Three</div>
</div>
```

```css
.item {
    opacity: 0;
    animation: fadeIn 0.5s ease forwards;
}

.item:nth-child(1) {
    animation-delay: 0s;
}

.item:nth-child(2) {
    animation-delay: 0.2s;
}

.item:nth-child(3) {
    animation-delay: 0.4s;
}

@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The items appear one after another because each one has a different delay.

### Delay and `animation-fill-mode`

When an animation has a delay, `animation-fill-mode` can affect the styles displayed during the delay period.

For example:

```css
.item {
    opacity: 0;
    animation: fadeIn 0.5s ease 0.5s forwards;
}
```

The `forwards` value controls the styles retained after the animation completes.

The `backwards` value can apply the styles from the first relevant keyframe during the delay.

```css
.item {
    animation: fadeIn 0.5s ease 0.5s backwards;
}
```

### Important Point

`animation-delay` controls **when an animation starts**. It does not control:

- How long the animation runs.
- How many times it repeats.
- The animation's speed pattern.

Those are controlled by other animation properties.

```text
animation-delay
    ↓
When does it start?

animation-duration
    ↓
How long does it run?

animation-iteration-count
    ↓
How many times does it run?

animation-timing-function
    ↓
How does its speed change?
```

> 💡 **Tip:** Animation delays are particularly useful for creating staggered entrance effects where multiple elements appear one after another.

> 💡 **Remember:** A positive delay waits before the animation starts, while a negative delay can make the animation behave as though it has already progressed along its timeline.

---

## Animation Iteration Count

The `animation-iteration-count` property specifies how many times a CSS animation should run.

By default, an animation runs **once**. The iteration count can be changed to make an animation repeat a specific number of times or continue indefinitely.

### Basic Syntax

```css
selector {
    animation-iteration-count: number;
}
```

For example:

```css
.box {
    animation-iteration-count: 3;
}
```

The animation runs three times.

### Default Value

The default value is:

```css
animation-iteration-count: 1;
```

This means the animation runs once.

For example:

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-iteration-count: 1;
}
```

### Repeating an Animation

A number greater than `1` repeats the animation.

```css
.box {
    animation-name: move;
    animation-duration: 1s;
    animation-iteration-count: 3;
}
```

The animation runs:

```text
Cycle 1
   ↓
Cycle 2
   ↓
Cycle 3
   ↓
Complete
```

### Using `infinite`

The `infinite` value makes the animation repeat continuously.

```css
.loader {
    animation-name: spin;
    animation-duration: 1s;
    animation-iteration-count: infinite;
}
```

The animation continues until it is stopped or the element is no longer animated.

### Loading Spinner Example

A common use of `infinite` is a loading spinner.

```css
.loader {
    width: 40px;
    height: 40px;
    border: 4px solid lightgray;
    border-top-color: steelblue;
    border-radius: 50%;

    animation:
        spin 1s linear infinite;
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

The spinner continuously rotates because the animation iteration count is `infinite`.

### Fractional Iteration Counts

The iteration count can also be a fractional number.

For example:

```css
.box {
    animation-iteration-count: 2.5;
}
```

This runs two complete cycles and then half of the next cycle.

For example:

```text
Cycle 1
   ↓
Cycle 2
   ↓
Half of Cycle 3
   ↓
Complete
```

Fractional iteration counts can be useful when an animation needs to stop partway through a cycle.

### Multiple Animations

Different iteration counts can be specified for multiple animations.

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
    animation-iteration-count: 3, 2;
}
```

Here:

```text
move → 3 times
fade → 2 times
```

The values correspond by position.

### Iteration Count with Shorthand

The iteration count can also be included in the `animation` shorthand.

```css
.box {
    animation: move 2s ease 0s 3;
}
```

Here:

```text
move
 ↓
Animation name

2s
 ↓
Duration

ease
 ↓
Timing function

0s
 ↓
Delay

3
 ↓
Iteration count
```

For an infinite animation:

```css
.loader {
    animation: spin 1s linear infinite;
}
```

### Iteration Count and Animation Direction

When an animation repeats, `animation-direction` can determine how successive iterations are played.

For example:

```css
.box {
    animation:
        move 1s ease infinite alternate;
}
```

With `alternate`, the animation plays forward during one cycle and backward during the next.

```text
Forward
   ↓
Backward
   ↓
Forward
   ↓
Backward
```

This can create a continuous back-and-forth effect.

### Practical Example

```html
<div class="box">
    Animate Me
</div>
```

```css
.box {
    animation:
        bounce 1s ease 0s 3;
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

The animation runs three times and then stops.

### Choosing an Iteration Count

The appropriate iteration count depends on the purpose of the animation.

```text
1
↓
One-time entrance or exit effect

2–3
↓
Short repeated effect

Several times
↓
Attention or feedback effect

infinite
↓
Continuous effects such as loading indicators
```

These are practical examples rather than strict rules.

### Important Point

`animation-iteration-count` controls **how many times the animation runs**.

It does not control:

- How long each cycle takes.
- How quickly the animation progresses.
- When the animation starts.
- The direction of the animation.

Those are controlled by other animation properties.

```text
animation-duration
    ↓
How long is one cycle?

animation-timing-function
    ↓
How does the speed change?

animation-delay
    ↓
When does it start?

animation-iteration-count
    ↓
How many cycles?

animation-direction
    ↓
Which direction does each cycle play?
```

> 💡 **Tip:** Use a finite iteration count for effects that should happen a specific number of times and `infinite` for effects that should continue until stopped.

> 💡 **Remember:** `animation-iteration-count` determines **how many times an animation cycle is played**.

---

## Animation Direction

The `animation-direction` property specifies the direction in which an animation's keyframes are played.

It controls whether the animation plays normally, in reverse, or alternates between forward and reverse directions when it repeats.

### Basic Syntax

```css
selector {
    animation-direction: value;
}
```

The default value is:

```css
animation-direction: normal;
```

### `normal`

The `normal` value plays the animation forward during every iteration.

```css
.box {
    animation:
        move 1s ease 0s 3 normal;
}
```

The animation follows the keyframes from the beginning to the end on every iteration.

```text
Forward
   ↓
Forward
   ↓
Forward
```

### `reverse`

The `reverse` value plays the animation backward.

```css
.box {
    animation:
        move 1s ease 0s 3 reverse;
}
```

The keyframes are played in the opposite direction.

```text
End
 ↓
Middle
 ↓
Start
```

### `alternate`

The `alternate` value switches direction on each iteration.

```css
.box {
    animation:
        move 1s ease 0s infinite alternate;
}
```

The animation plays:

```text
Forward
   ↓
Backward
   ↓
Forward
   ↓
Backward
```

This is useful for creating back-and-forth movement.

### `alternate-reverse`

The `alternate-reverse` value also alternates between directions, but the first iteration plays in reverse.

```css
.box {
    animation:
        move 1s ease 0s infinite alternate-reverse;
}
```

The sequence begins with a reverse iteration:

```text
Backward
   ↓
Forward
   ↓
Backward
   ↓
Forward
```

### Comparing Direction Values

| Value | Behavior |
| --- | --- |
| `normal` | Plays forward on every iteration |
| `reverse` | Plays backward on every iteration |
| `alternate` | Alternates forward and backward |
| `alternate-reverse` | Starts backward, then alternates |

### Direction with `animation-iteration-count`

The effect of `animation-direction` becomes especially useful when an animation repeats.

For example:

```css
.box {
    animation:
        move 1s ease 0s 4 alternate;
}
```

The four iterations behave like:

```text
Iteration 1 → Forward
Iteration 2 → Backward
Iteration 3 → Forward
Iteration 4 → Backward
```

### Direction with `infinite`

`alternate` is commonly combined with `infinite` for continuous back-and-forth effects.

```css
.box {
    animation:
        move 1s ease 0s infinite alternate;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The element repeatedly moves between the two positions.

### Practical Example

```html
<div class="box">
    Move Me
</div>
```

```css
.box {
    width: 80px;
    height: 80px;
    background-color: steelblue;

    animation:
        move 1s ease-in-out infinite alternate;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(150px);
    }
}
```

The box moves to the right and then returns to its original position repeatedly.

### Direction with Shorthand

The direction can be included in the `animation` shorthand.

```css
.box {
    animation: move 1s ease 0s infinite alternate;
}
```

Here:

```text
move
 ↓
Animation name

1s
 ↓
Duration

ease
 ↓
Timing function

0s
 ↓
Delay

infinite
 ↓
Iteration count

alternate
 ↓
Direction
```

### Important Point

`animation-direction` does not define the animation stages.

The `@keyframes` rule defines the stages:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The `animation-direction` property determines how those stages are played.

```text
@keyframes
    ↓
Defines the stages

animation-direction
    ↓
Controls their playback direction
```

> 💡 **Tip:** Use `alternate` when an element needs to move back and forth without having to create separate forward and reverse keyframes.

> 💡 **Remember:** `normal` plays forward, `reverse` plays backward, `alternate` switches direction after each iteration, and `alternate-reverse` starts in reverse and then alternates.

---

## Animation Fill Mode

The `animation-fill-mode` property specifies how an element should be styled before an animation starts and after an animation finishes.

It is especially useful when an animation has a delay or when the final keyframe styles should remain after the animation completes.

### Basic Syntax

```css
selector {
    animation-fill-mode: value;
}
```

The main values are:

```text
none
forwards
backwards
both
```

### `none`

The `none` value is the default.

```css
.box {
    animation-fill-mode: none;
}
```

The element does not retain the styles from the animation's keyframes before or after the animation.

### `forwards`

The `forwards` value causes the element to retain the styles from the final keyframe after the animation finishes.

```css
.box {
    animation: move 2s ease forwards;
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

After the animation finishes, the element remains at the position defined by the final keyframe.

```text
Animation starts
      ↓
Animation runs
      ↓
Final keyframe
      ↓
Final styles remain
```

### `backwards`

The `backwards` value applies the styles from the first relevant keyframe during the animation's delay period.

```css
.box {
    animation: move 2s ease 1s backwards;
}
```

The animation waits for `1s`, and during that delay the element can use the styles from the starting keyframe.

### `both`

The `both` value combines the behavior of `forwards` and `backwards`.

```css
.box {
    animation: move 2s ease 1s both;
}
```

This means:

```text
Before animation
      ↓
Use starting keyframe styles

Animation runs
      ↓
Animation stages

After animation
      ↓
Keep final keyframe styles
```

### Comparing Fill Modes

| Value | Before Animation | After Animation |
| --- | --- | --- |
| `none` | No keyframe styles | No keyframe styles |
| `forwards` | No keyframe styles | Keeps final keyframe |
| `backwards` | Uses starting keyframe during delay | No final keyframe retention |
| `both` | Uses starting keyframe during delay | Keeps final keyframe |

### Fill Mode with a Delay

`animation-fill-mode` becomes particularly useful when an animation has a delay.

```css
.box {
    animation:
        fadeIn 1s ease 1s backwards;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Here:

```text
0s – 1s
    ↓
Delay
    ↓
Starting keyframe styles

1s – 2s
    ↓
Animation runs

After 2s
    ↓
Animation completes
```

### Fill Mode with `forwards`

A common use is keeping an element in its final animated state.

```css
.card {
    animation: slideIn 0.6s ease forwards;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

Without `forwards`, the element may return to its pre-animation styles after the animation finishes.

### Fill Mode with `both`

`both` is useful when an animation has both a delay and a final state that should be retained.

```css
.card {
    animation: slideIn 0.6s ease 0.3s both;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The card uses the starting keyframe during the delay and keeps the final keyframe after the animation completes.

### Fill Mode with Shorthand

The fill mode can be included in the `animation` shorthand.

```css
.box {
    animation: move 2s ease 0s 1 normal forwards;
}
```

Here:

```text
move
    ↓
Animation name

2s
    ↓
Duration

ease
    ↓
Timing function

0s
    ↓
Delay

1
    ↓
Iteration count

normal
    ↓
Direction

forwards
    ↓
Fill mode
```

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background-color: steelblue;
    color: white;

    animation:
        slideIn 0.8s ease 0.5s both;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

The `both` value ensures that the starting keyframe is applied during the delay and the final keyframe remains after the animation finishes.

### Important Point

`animation-fill-mode` controls the styles applied outside the active animation period.

```text
Before animation
      ↓
backwards

During animation
      ↓
@keyframes

After animation
      ↓
forwards
```

The `both` value combines the before-animation and after-animation behavior.

> 💡 **Tip:** `forwards` is commonly useful for entrance animations when the element should remain in its final state after the animation finishes.

> 💡 **Remember:** `animation-fill-mode` controls what styles are retained **before and after an animation**, while `@keyframes` defines the actual animation stages.

---

## Animation Play State

The `animation-play-state` property controls whether a CSS animation is currently running or paused.

It is useful when an animation needs to be temporarily stopped and then continued without restarting it from the beginning.

### Basic Syntax

```css
selector {
    animation-play-state: value;
}
```

The two main values are:

```text
running
paused
```

### `running`

The `running` value means that the animation is playing.

```css
.box {
    animation-play-state: running;
}
```

This is the default state.

For example:

```css
.box {
    animation: move 2s ease infinite;
    animation-play-state: running;
}
```

The animation continues to play normally.

### `paused`

The `paused` value stops the animation.

```css
.box {
    animation: move 2s ease infinite;
    animation-play-state: paused;
}
```

When the animation is paused, its current position is retained.

It does not restart from the beginning when it is paused.

### Pausing an Animation on Hover

A common use is to pause an animation when the user moves the pointer over an element.

```css
.box {
    animation: move 2s ease infinite alternate;
}

.box:hover {
    animation-play-state: paused;
}
```

The animation plays normally until the user hovers over the element.

```text
Animation running
       ↓
     Hover
       ↓
Animation paused
       ↓
Leave hover
       ↓
Animation continues
```

### Resuming an Animation

The animation can be started again by changing the value back to `running`.

```css
.box {
    animation: move 2s ease infinite;
    animation-play-state: paused;
}

.box.active {
    animation-play-state: running;
}
```

When the `.active` class is applied, the animation continues.

### Play State Does Not Restart the Animation

Consider:

```css
.box {
    animation: move 5s linear;
}

.box:hover {
    animation-play-state: paused;
}
```

If the animation is paused halfway through, it remains at that point.

When the state changes back to:

```css
animation-play-state: running;
```

the animation continues from the paused position.

```text
Start
  ↓
Animation runs
  ↓
50%
  ↓
Pause
  ↓
Remains at 50%
  ↓
Resume
  ↓
Continues from 50%
```

### Play State with Infinite Animations

`animation-play-state` is particularly useful with animations that repeat continuously.

```css
.loader {
    animation: spin 1s linear infinite;
}

.loader:hover {
    animation-play-state: paused;
}
```

The spinner stops rotating while it is hovered.

### Practical Example

```html
<div class="box">
    Hover to Pause
</div>
```

```css
.box {
    width: 100px;
    height: 100px;
    background-color: steelblue;

    animation:
        move 2s ease-in-out infinite alternate;
}

.box:hover {
    animation-play-state: paused;
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

The box continuously moves between two positions. Hovering over it pauses the animation, and moving the pointer away allows it to continue.

### Play State with JavaScript

The `animation-play-state` property can also be changed through JavaScript when animation control needs to depend on application logic.

For example:

```javascript
element.style.animationPlayState = "paused";
```

The animation can be resumed with:

```javascript
element.style.animationPlayState = "running";
```

CSS is still responsible for defining the animation itself.

### Using Play State with Multiple Animations

When multiple animations are applied, play states can also be specified as comma-separated values.

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
    animation-play-state: running, paused;
}
```

Here:

```text
move → running
fade → paused
```

The values correspond by position.

### Play State with the Animation Shorthand

`animation-play-state` is an important animation property, but it is generally written separately when controlling the current running or paused state.

For example:

```css
.box {
    animation: move 2s ease infinite;
    animation-play-state: paused;
}
```

This makes the current playback state explicit.

### Important Point

`animation-play-state` controls whether an animation is running or paused.

```text
running
   ↓
Animation continues

paused
   ↓
Animation stops at its current position
```

It does not change:

- The animation duration.
- The animation timing function.
- The number of iterations.
- The keyframes themselves.

Those are controlled by other animation properties.

> 💡 **Tip:** `animation-play-state: paused` is useful for interactive animations such as loaders, decorative movement, and hover-controlled effects.

> 💡 **Remember:** Pausing an animation does not reset it. When it is changed back to `running`, the animation continues from its current position.

---

## Animation Shorthand

The `animation` property is a shorthand property that allows multiple animation properties to be written in a single declaration.

Instead of writing each animation property separately, the shorthand can combine them into one line.

### Individual Animation Properties

For example:

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-timing-function: ease;
    animation-delay: 0s;
    animation-iteration-count: 1;
    animation-direction: normal;
    animation-fill-mode: none;
    animation-play-state: running;
}
```

The same basic configuration can be written using the shorthand:

```css
.box {
    animation: move 2s ease 0s 1 normal none running;
}
```

### Basic Syntax

The general shorthand syntax is:

```css
animation: name duration timing-function delay iteration-count direction fill-mode play-state;
```

For example:

```css
.box {
    animation: move 2s ease 0s 1 normal forwards running;
}
```

The values represent:

```text
move
    ↓
Animation name

2s
    ↓
Animation duration

ease
    ↓
Timing function

0s
    ↓
Delay

1
    ↓
Iteration count

normal
    ↓
Direction

forwards
    ↓
Fill mode

running
    ↓
Play state
```

### Basic Shorthand

You do not have to specify every value.

For example:

```css
.box {
    animation: move 2s;
}
```

This specifies:

```text
Animation name → move
Duration       → 2s
```

The remaining animation properties use their default values unless specified elsewhere.

### Shorthand with Timing Function

```css
.box {
    animation: move 2s ease;
}
```

Here:

```text
move → Name
2s   → Duration
ease → Timing function
```

### Shorthand with Delay

```css
.box {
    animation: move 2s ease 0.5s;
}
```

Here:

```text
move → Name
2s   → Duration
ease → Timing function
0.5s → Delay
```

### Shorthand with Iteration Count

```css
.box {
    animation: move 2s ease 0s 3;
}
```

The animation runs three times.

```text
move → Name
2s   → Duration
ease → Timing function
0s   → Delay
3    → Iteration count
```

### Infinite Animation

For a continuously repeating animation:

```css
.loader {
    animation: spin 1s linear infinite;
}
```

Here:

```text
spin     → Animation name
1s       → Duration
linear   → Timing function
infinite → Iteration count
```

### Shorthand with Direction

```css
.box {
    animation: move 1s ease 0s infinite alternate;
}
```

The animation continuously moves forward and backward.

### Shorthand with Fill Mode

```css
.box {
    animation: slideIn 0.6s ease 0s 1 normal forwards;
}
```

The `forwards` value causes the element to retain the final keyframe styles after the animation completes.

### Multiple Animations

Multiple animations can also be specified using commas.

```css
.box {
    animation:
        move 2s ease,
        fade 1s linear;
}
```

The first animation is:

```text
move
2s
ease
```

The second animation is:

```text
fade
1s
linear
```

### Multiple Animations with More Properties

Each animation can have its own settings.

```css
.box {
    animation:
        move 2s ease 0s 1,
        fade 1s linear 0.5s 2;
}
```

Here:

```text
move → 2s, ease, 0s delay, 1 iteration

fade → 1s, linear, 0.5s delay, 2 iterations
```

### Shorthand and Individual Properties

The shorthand can be used together with individual animation properties when appropriate.

For example:

```css
.box {
    animation: move 2s ease;
    animation-iteration-count: infinite;
}
```

However, when using the shorthand, remember that omitted values can reset corresponding animation properties to their initial values.

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    animation: slideIn 1s ease-out 0.2s 1 normal forwards;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

This single declaration specifies:

```text
Animation name      → slideIn
Duration            → 1s
Timing function     → ease-out
Delay               → 0.2s
Iteration count     → 1
Direction           → normal
Fill mode           → forwards
```

### Important Point

The `animation` shorthand is useful because it keeps related animation settings together.

```text
animation
    ↓
name
duration
timing function
delay
iteration count
direction
fill mode
play state
```

You can start with a simple declaration:

```css
animation: move 2s;
```

and add additional values when more control is required.

> 💡 **Tip:** Use the shorthand for concise CSS, but use individual properties when separating the animation settings makes the code easier to understand or maintain.

> 💡 **Remember:** The `animation` shorthand combines multiple animation properties into one declaration. You do not need to specify every value.

---

## Multiple Animations

CSS allows multiple animations to run on the same element at the same time.

Multiple animations are specified by separating individual animation declarations with commas.

### Basic Syntax

```css
selector {
    animation:
        animation-one duration,
        animation-two duration;
}
```

For example:

```css
.box {
    animation:
        move 2s ease,
        fade 2s ease;
}
```

Here, both animations are applied to the `.box` element.

### Defining Multiple Keyframes

Each animation should have its own `@keyframes` rule.

```css
.box {
    animation:
        move 2s ease,
        fade 2s ease;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
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

The two animations work together:

```text
move
 ↓
Changes position

fade
 ↓
Changes opacity
```

### Different Durations

Each animation can have a different duration.

```css
.box {
    animation:
        move 2s ease,
        fade 1s ease;
}
```

Here:

```text
move → 2 seconds
fade → 1 second
```

The animations can therefore complete at different times.

### Different Timing Functions

Each animation can use its own timing function.

```css
.box {
    animation:
        move 2s ease-out,
        fade 1s linear;
}
```

Here:

```text
move → ease-out
fade → linear
```

### Different Delays

Animations can also have different delays.

```css
.box {
    animation:
        move 2s ease 0s,
        fade 1s ease 0.5s;
}
```

Here:

```text
move → starts immediately
fade → starts after 0.5 seconds
```

### Different Iteration Counts

Each animation can repeat a different number of times.

```css
.box {
    animation:
        move 2s ease 0s 1,
        fade 1s ease 0s 3;
}
```

Here:

```text
move → runs once
fade → runs three times
```

### Combining Multiple Animation Properties

When multiple animations are used, the values of individual animation properties correspond by position.

For example:

```css
.box {
    animation-name: move, fade;
    animation-duration: 2s, 1s;
    animation-timing-function: ease-out, linear;
    animation-delay: 0s, 0.5s;
    animation-iteration-count: 1, 3;
}
```

The first values belong to `move`:

```text
move
 ↓
2s
 ↓
ease-out
 ↓
0s
 ↓
1 iteration
```

The second values belong to `fade`:

```text
fade
 ↓
1s
 ↓
linear
 ↓
0.5s
 ↓
3 iterations
```

### Multiple Animations with Shorthand

Multiple animations can be written using the `animation` shorthand.

```css
.box {
    animation:
        move 2s ease,
        fade 1s linear;
}
```

Each animation is separated by a comma.

### Combining Transform and Opacity

A common use of multiple animations is combining movement and opacity.

```css
.card {
    animation:
        slideIn 0.6s ease-out,
        fadeIn 0.6s ease;
}

@keyframes slideIn {
    from {
        transform: translateY(30px);
    }

    to {
        transform: translateY(0);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

The card moves into position while becoming visible.

### Multiple Animations with Different Keyframes

Different animations can affect different properties.

```css
.box {
    animation:
        move 2s ease-in-out infinite alternate,
        pulse 1s ease-in-out infinite;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}

@keyframes pulse {
    from {
        opacity: 0.6;
    }

    to {
        opacity: 1;
    }
}
```

This creates two simultaneous effects:

```text
Movement
    +
Opacity change
```

### Practical Example

```html
<div class="box">
    CSS Animation
</div>
```

```css
.box {
    width: 120px;
    padding: 20px;
    background-color: steelblue;
    color: white;

    animation:
        slideIn 1s ease-out,
        fadeIn 1s ease;
}

@keyframes slideIn {
    from {
        transform: translateX(-50px);
    }

    to {
        transform: translateX(0);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

The element simultaneously:

- Moves into position.
- Changes from transparent to visible.

### Important Point

Multiple animations provide a way to combine independent animation effects on the same element.

```text
Element
   ↓
Animation 1 → Movement
Animation 2 → Opacity
Animation 3 → Color
```

However, care should be taken when multiple animations modify the same CSS property, because their effects can interact or conflict.

> 💡 **Tip:** Use multiple animations when separate effects need to run together, such as movement combined with opacity.

> 💡 **Remember:** Separate animations are separated with commas, and when individual animation properties contain multiple values, those values correspond to the animations by position.

---

## Animations with Transform

The `transform` property can be used with CSS animations to create movement, rotation, scaling, and other visual transformations.

Because `transform` changes the visual appearance of an element without changing the normal document flow, it is commonly used for smooth animation effects.

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

The element moves horizontally from its original position to a position `200px` to the right.

### Moving with `translateX()`

`translateX()` moves an element horizontally.

```css
@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(150px);
    }
}
```

Apply the animation:

```css
.box {
    animation: slide 1s ease;
}
```

### Moving with `translateY()`

`translateY()` moves an element vertically.

```css
@keyframes slideUp {
    from {
        transform: translateY(50px);
    }

    to {
        transform: translateY(0);
    }
}
```

This is useful for entrance effects.

```css
.card {
    animation: slideUp 0.6s ease-out;
}
```

### Moving in Both Directions

`translate()` can change both horizontal and vertical position.

```css
@keyframes move {
    from {
        transform: translate(0, 0);
    }

    to {
        transform: translate(100px, 50px);
    }
}
```

### Scaling with `scale()`

The `scale()` function changes the visual size of an element.

```css
@keyframes grow {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(1.2);
    }
}
```

Apply the animation:

```css
.box {
    animation: grow 0.8s ease;
}
```

The element grows from its original scale to `1.2` times its original size.

### Shrinking with `scale()`

The same function can be used to create a shrinking effect.

```css
@keyframes shrink {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(0.8);
    }
}
```

### Rotating with `rotate()`

The `rotate()` function rotates an element.

```css
@keyframes rotate {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
```

Apply it:

```css
.icon {
    animation: rotate 2s linear;
}
```

### Continuous Rotation

A rotation can be repeated indefinitely.

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

This is commonly used for loading indicators.

### Combining Transform Functions

Multiple transform functions can be used in the same keyframe.

```css
@keyframes entrance {
    from {
        transform: translateY(30px) scale(0.9);
    }

    to {
        transform: translateY(0) scale(1);
    }
}
```

The element:

```text
Moves upward
    +
Grows to its normal size
```

### Combining Transform with Opacity

Transform animations can be combined with other properties.

```css
@keyframes fadeSlide {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

Apply it:

```css
.card {
    animation: fadeSlide 0.6s ease-out;
}
```

This creates a common entrance effect.

### Using Multiple Transform Stages

Transform values can change at multiple points in an animation.

```css
@keyframes bounce {
    0% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-40px);
    }

    75% {
        transform: translateY(0);
    }

    100% {
        transform: translateY(-10px);
    }
}
```

This allows more complex movement than a simple `from` and `to` animation.

### Combining Rotation and Scaling

Different transform functions can be combined.

```css
@keyframes effect {
    from {
        transform: rotate(0deg) scale(1);
    }

    to {
        transform: rotate(360deg) scale(1.2);
    }
}
```

Apply the animation:

```css
.box {
    animation: effect 2s ease;
}
```

### Using `transform-origin`

The `transform-origin` property determines the point around which a transformation occurs.

For example:

```css
.box {
    transform-origin: center;
    animation: rotate 2s linear;
}
```

Another example:

```css
.box {
    transform-origin: left center;
}
```

This can change the visual behavior of rotation and scaling.

### Practical Example

```html
<div class="card">
    CSS Animation
</div>
```

```css
.card {
    width: 200px;
    padding: 30px;
    background-color: steelblue;
    color: white;

    animation: cardEntrance 0.8s ease-out;
}

@keyframes cardEntrance {
    from {
        opacity: 0;
        transform: translateY(40px) scale(0.95);
    }

    to {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
}
```

The card starts slightly lower and smaller, then moves into position while becoming visible.

### Transform Animation and Layout

Transformations are visual transformations and generally do not change the normal layout position of surrounding elements.

For example:

```css
.box {
    animation: move 1s ease;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The box visually moves, but the space it occupies in the normal layout remains based on its original position.

This makes transforms useful for many movement effects.

### Important Point

The `transform` property defines the visual transformation:

```css
transform: translateX(100px);
```

The animation defines how that transformation changes over time:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

Together:

```text
transform
    ↓
Defines the visual change

@keyframes
    ↓
Defines how the value changes over time

animation
    ↓
Controls playback
```

> 💡 **Tip:** `transform` is especially useful for movement, scaling, and rotation effects because these transformations can often be animated without changing the normal document flow.

> 💡 **Remember:** Common transform functions used in animations include `translate()`, `scale()`, and `rotate()`.

---

## Animations with Colors

CSS animations can be used to smoothly change color-related properties over time.

Colors can be changed using `@keyframes` in the same way as other CSS properties.

### Basic Example

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

The background color gradually changes from `steelblue` to `darkblue`.

### Animating `background-color`

The `background-color` property is commonly used with animations.

```css
.box {
    animation: backgroundChange 2s ease;
}

@keyframes backgroundChange {
    from {
        background-color: lightblue;
    }

    to {
        background-color: darkblue;
    }
}
```

### Animating `color`

The `color` property can be animated to change text color.

```css
.text {
    animation: textColor 2s ease;
}

@keyframes textColor {
    from {
        color: black;
    }

    to {
        color: white;
    }
}
```

### Animating `border-color`

Border colors can also be animated.

```css
.box {
    border: 3px solid gray;
    animation: borderChange 2s ease;
}

@keyframes borderChange {
    from {
        border-color: gray;
    }

    to {
        border-color: steelblue;
    }
}
```

### Multiple Color Properties

Multiple color properties can be changed within the same animation.

```css
.card {
    animation: colorShift 2s ease;
}

@keyframes colorShift {
    from {
        background-color: white;
        color: black;
        border-color: gray;
    }

    to {
        background-color: steelblue;
        color: white;
        border-color: darkblue;
    }
}
```

The animation changes:

```text
Background color
       +
Text color
       +
Border color
```

### Using Percentage Keyframes

Percentage keyframes allow several color stages.

```css
.box {
    animation: colors 3s ease;
}

@keyframes colors {
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

The animation passes through three color stages.

```text
0%
 ↓
Steel Blue

50%
 ↓
Purple

100%
 ↓
Dark Blue
```

### Repeating Color Animations

Color animations can repeat using `animation-iteration-count`.

```css
.box {
    animation: colorPulse 2s ease-in-out infinite alternate;
}

@keyframes colorPulse {
    from {
        background-color: steelblue;
    }

    to {
        background-color: lightblue;
    }
}
```

The element repeatedly changes between the two colors.

### Color Animation with Transform

Color changes can be combined with transformations.

```css
.box {
    animation: colorMove 2s ease-in-out;
}

@keyframes colorMove {
    from {
        background-color: steelblue;
        transform: translateX(0);
    }

    to {
        background-color: darkblue;
        transform: translateX(100px);
    }
}
```

The element changes color while moving horizontally.

### Color Animation with Opacity

Colors can also be combined with opacity.

```css
.box {
    animation: fadeColor 2s ease;
}

@keyframes fadeColor {
    from {
        background-color: steelblue;
        opacity: 0;
    }

    to {
        background-color: darkblue;
        opacity: 1;
    }
}
```

The element becomes visible while its background color changes.

### Practical Example

```html
<div class="status">
    Processing
</div>
```

```css
.status {
    padding: 15px 20px;
    color: white;

    animation: statusChange 2s ease-in-out infinite alternate;
}

@keyframes statusChange {
    from {
        background-color: steelblue;
    }

    to {
        background-color: darkblue;
    }
}
```

The status element continuously changes between two background colors.

### Color Animations with Multiple Stages

More complex effects can use several stages.

```css
.notification {
    animation: alertColors 3s ease;
}

@keyframes alertColors {
    0% {
        background-color: steelblue;
    }

    25% {
        background-color: lightblue;
    }

    50% {
        background-color: orange;
    }

    75% {
        background-color: gold;
    }

    100% {
        background-color: steelblue;
    }
}
```

This creates a sequence of color changes throughout the animation.

### Important Point

Color animations work by changing color properties inside `@keyframes`.

```text
@keyframes
    ↓
Color at beginning
    ↓
Color at intermediate stages
    ↓
Color at end
```

The animation controls how those values change over time.

Common color properties used in animations include:

```text
color
background-color
border-color
```

> 💡 **Tip:** Color animations are useful for visual feedback, status indicators, attention effects, and decorative effects. Keep the changes readable and avoid excessive color movement.

> 💡 **Remember:** Color properties can be animated just like transform and opacity values by defining their different values inside `@keyframes`.

---

## Animations with Opacity

The `opacity` property can be used with CSS animations to control the visibility of an element over time.

The value of `opacity` ranges from `0` to `1`:

```text
0
↓
Completely transparent

0.5
↓
Partially transparent

1
↓
Completely visible
```

### Basic Example

```css
.box {
    animation: fadeIn 1s ease;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

The element starts transparent and gradually becomes fully visible.

### Fade-In Animation

A fade-in effect can be created by changing opacity from `0` to `1`.

```css
.card {
    animation: fadeIn 0.6s ease;
}

@keyframes fadeIn {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}
```

### Fade-Out Animation

A fade-out effect can be created by changing opacity from `1` to `0`.

```css
.card {
    animation: fadeOut 0.6s ease;
}

@keyframes fadeOut {
    from {
        opacity: 1;
    }

    to {
        opacity: 0;
    }
}
```

The element gradually becomes transparent.

### Partial Opacity

An animation does not have to use only `0` and `1`.

For example:

```css
.box {
    animation: fade 2s ease;
}

@keyframes fade {
    from {
        opacity: 0.3;
    }

    to {
        opacity: 1;
    }
}
```

The element starts partially transparent and becomes fully visible.

### Multiple Opacity Stages

Percentage keyframes can be used to create multiple opacity stages.

```css
.box {
    animation: pulse 2s ease-in-out;
}

@keyframes pulse {
    0% {
        opacity: 1;
    }

    50% {
        opacity: 0.4;
    }

    100% {
        opacity: 1;
    }
}
```

The element becomes partially transparent and then returns to full visibility.

### Repeating Opacity Animation

Opacity animations can be repeated.

```css
.notification {
    animation: blink 1s ease-in-out infinite;
}

@keyframes blink {
    from {
        opacity: 1;
    }

    to {
        opacity: 0.3;
    }
}
```

The element repeatedly changes between full and partial visibility.

### Opacity with Transform

Opacity is often combined with `transform` to create entrance effects.

```css
.card {
    animation: slideFadeIn 0.6s ease-out;
}

@keyframes slideFadeIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The card:

```text
Starts lower
    +
Starts transparent
    ↓
Moves upward
    +
Becomes visible
```

### Opacity with Scale

Opacity can also be combined with scaling.

```css
.box {
    animation: scaleFade 0.5s ease;
}

@keyframes scaleFade {
    from {
        opacity: 0;
        transform: scale(0.9);
    }

    to {
        opacity: 1;
        transform: scale(1);
    }
}
```

This creates a subtle appearance effect.

### Using `animation-fill-mode`

When an animation changes opacity, `animation-fill-mode` can be useful for keeping the final opacity after the animation finishes.

```css
.card {
    animation: fadeIn 0.6s ease forwards;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

The `forwards` value keeps the final keyframe styles after the animation completes.

### Practical Example

```html
<div class="message">
    Welcome!
</div>
```

```css
.message {
    padding: 20px;
    background-color: steelblue;
    color: white;

    animation: messageIn 0.8s ease-out;
}

@keyframes messageIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The message smoothly appears while moving into its final position.

### Important Point

The `opacity` property controls the transparency of an element:

```text
opacity: 0
    ↓
Invisible

opacity: 0.5
    ↓
Partially transparent

opacity: 1
    ↓
Fully visible
```

When used inside `@keyframes`, it can create effects such as:

```text
Fade in
Fade out
Pulse
Blink
Entrance effects
```

> 💡 **Tip:** Combining `opacity` with `transform` is a common way to create subtle entrance and exit effects.

> 💡 **Remember:** `opacity` controls transparency, while the animation determines how that value changes over time.

---

## Practical Examples

The following examples demonstrate how CSS animations can be used to create common interface effects.

### 1. Fade-In Effect

A fade-in animation gradually makes an element visible.

```css
.card {
    animation: fadeIn 0.6s ease;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

### 2. Slide-In Effect

An element can enter from the side using `transform`.

```css
.card {
    animation: slideIn 0.6s ease-out;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }

    to {
        opacity: 1;
        transform: translateX(0);
    }
}
```

### 3. Slide-Up Effect

This effect is commonly used for cards, messages, and sections.

```css
.card {
    animation: slideUp 0.6s ease-out;
}

@keyframes slideUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

### 4. Rotating Loader

A continuously rotating element can be created using `rotate()` and `infinite`.

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
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
```

### 5. Pulsing Effect

A pulsing effect can repeatedly change the scale of an element.

```css
.notification {
    animation: pulse 1s ease-in-out infinite;
}

@keyframes pulse {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }

    100% {
        transform: scale(1);
    }
}
```

This can be used to draw attention to notifications or status indicators.

### 6. Bounce Effect

A bounce can be created using multiple keyframe stages.

```css
.box {
    animation: bounce 1s ease-in-out infinite;
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

### 7. Color Change

An element can gradually change its background color.

```css
.box {
    animation: colorChange 2s ease-in-out infinite alternate;
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

### 8. Fade and Scale

Opacity and transform can be combined for a subtle entrance effect.

```css
.card {
    animation: fadeScale 0.6s ease-out;
}

@keyframes fadeScale {
    from {
        opacity: 0;
        transform: scale(0.9);
    }

    to {
        opacity: 1;
        transform: scale(1);
    }
}
```

### 9. Staggered Card Animation

Different delays can make several elements appear one after another.

```html
<div class="card">Card 1</div>
<div class="card">Card 2</div>
<div class="card">Card 3</div>
```

```css
.card {
    opacity: 0;
    animation: cardIn 0.5s ease forwards;
}

.card:nth-child(1) {
    animation-delay: 0s;
}

.card:nth-child(2) {
    animation-delay: 0.2s;
}

.card:nth-child(3) {
    animation-delay: 0.4s;
}

@keyframes cardIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

The cards appear one after another.

```text
Card 1
   ↓
Card 2
   ↓
Card 3
```

### 10. Back-and-Forth Movement

The `alternate` direction can create continuous movement between two positions.

```css
.box {
    animation: move 1.5s ease-in-out infinite alternate;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The element moves forward and then backward repeatedly.

### 11. Attention-Wave Effect

An element can combine rotation and translation to create a small attention effect.

```css
.button {
    animation: attention 0.6s ease;
}

@keyframes attention {
    0% {
        transform: rotate(0deg);
    }

    25% {
        transform: rotate(-3deg);
    }

    50% {
        transform: rotate(3deg);
    }

    75% {
        transform: rotate(-2deg);
    }

    100% {
        transform: rotate(0deg);
    }
}
```

This type of effect should be used sparingly.

### 12. Complete Animated Card

A card can combine several animation concepts.

```html
<div class="product-card">
    <h2>Product</h2>
    <p>Animated product card.</p>
    <button>View Product</button>
</div>
```

```css
.product-card {
    width: 250px;
    padding: 24px;
    background-color: white;
    border: 1px solid lightgray;

    animation: cardEntrance 0.7s ease-out;
}

.product-card button {
    animation: buttonPulse 1.5s ease-in-out 0.7s infinite alternate;
}

@keyframes cardEntrance {
    from {
        opacity: 0;
        transform: translateY(30px) scale(0.95);
    }

    to {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
}

@keyframes buttonPulse {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(1.04);
    }
}
```

This example combines:

```text
Opacity
   +
Transform
   +
Animation duration
   +
Animation delay
   +
Repeated animation
```

### 13. Pausable Animation

An animation can be paused using `animation-play-state`.

```css
.loader {
    animation: spin 1s linear infinite;
}

.loader:hover {
    animation-play-state: paused;
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

The animation stops while the user hovers over the loader.

### 14. Entrance Animation with Fill Mode

`forwards` can keep an element in its final animated state.

```css
.message {
    animation: messageIn 0.6s ease forwards;
}

@keyframes messageIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

### 15. Combining Multiple Animations

Multiple animations can run on the same element.

```css
.box {
    animation:
        move 2s ease-in-out infinite alternate,
        colorChange 2s ease-in-out infinite alternate;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
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

The element moves while its background color changes.

### Accessibility Example

Animations should consider users who prefer reduced motion.

```css
.card {
    animation: slideIn 0.6s ease-out;
}

@media (prefers-reduced-motion: reduce) {
    .card {
        animation: none;
    }
}
```

This allows the animation to be disabled for users who have requested reduced motion.

### Practical Example Checklist

```text
⬜ Fade-in effect
⬜ Slide-in effect
⬜ Slide-up effect
⬜ Rotating loader
⬜ Pulsing effect
⬜ Bounce effect
⬜ Color change
⬜ Fade and scale
⬜ Staggered animation
⬜ Back-and-forth movement
⬜ Attention effect
⬜ Complete animated card
⬜ Pausable animation
⬜ Fill-mode example
⬜ Multiple animations
⬜ Reduced-motion support
```

> 💡 **Tip:** Start with simple effects such as fade, slide, scale, and rotate before combining several animation properties.

> 💡 **Remember:** Practical animation design is about combining the animation properties appropriately rather than using as many effects as possible.

---

## Key Takeaways

- CSS animations allow CSS properties to change automatically over time.
- The `@keyframes` rule defines the stages of an animation.
- The `animation` property applies and controls an animation.
- `animation-name` specifies which `@keyframes` rule to use.
- `animation-duration` defines how long one animation cycle takes.
- `animation-timing-function` controls the speed pattern of the animation.
- `animation-delay` specifies how long to wait before the animation starts.
- `animation-iteration-count` controls how many times the animation runs.
- `animation-direction` controls the playback direction of repeated animations.
- `animation-fill-mode` controls the styles applied before and after an animation.
- `animation-play-state` allows an animation to be paused or resumed.
- The `animation` shorthand combines multiple animation properties into one declaration.
- Multiple animations can be applied to the same element using comma-separated declarations.
- `transform` is commonly used with animations for movement, scaling, and rotation.
- Color properties such as `color`, `background-color`, and `border-color` can be animated.
- `opacity` can be animated to create fade and visibility effects.
- CSS animations can create entrance effects, loaders, pulses, rotations, and other visual effects.
- `animation-iteration-count: infinite` can be used for continuously repeating effects.
- `animation-direction: alternate` can create back-and-forth movement.
- `animation-fill-mode: forwards` can keep the final keyframe styles after an animation finishes.
- `animation-play-state: paused` pauses an animation at its current position.
- Multiple animation stages can be created using percentage-based keyframes such as `0%`, `50%`, and `100%`.
- CSS animations can often create visual effects without JavaScript.
- Animations should have a clear purpose and should not unnecessarily distract users.
- The `prefers-reduced-motion` media feature can be used to reduce or disable animations for users who prefer less motion.

### Core Animation Structure

```text
@keyframes
    ↓
Defines animation stages
    ↓
animation-name
    ↓
Identifies the animation
    ↓
animation-duration
    ↓
Defines the cycle duration
    ↓
Other animation properties
    ↓
Control playback behavior
```

### Important Properties

```text
animation-name
animation-duration
animation-timing-function
animation-delay
animation-iteration-count
animation-direction
animation-fill-mode
animation-play-state
animation
```

### Common Animation Pattern

```css
.box {
    animation: slideIn 0.6s ease-out;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

### CSS Animation vs Transition

```text
CSS Transition
    ↓
Usually handles a change between states

CSS Animation
    ↓
Can define multiple stages
    ↓
Can start automatically
    ↓
Can repeat
    ↓
Can control direction and playback
```

> 💡 **Remember:** `@keyframes` defines **what happens**, while the `animation` properties control **how the animation runs**.

> 💡 **Key idea:** Good CSS animations should improve visual feedback, communication, or user experience rather than simply adding movement.

---

## References

The following references provide reliable information about CSS animations and related animation properties.

### MDN Web Docs

- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations)
- [animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
- [animation-name](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name)
- [animation-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration)
- [animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
- [animation-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)
- [animation-iteration-count](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)
- [animation-direction](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction)
- [animation-fill-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode)
- [animation-play-state](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state)
- [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)

### W3C / CSS Specifications

- [CSS Animations](https://drafts.csswg.org/css-animations/)
- [CSS Transforms](https://drafts.csswg.org/css-transforms/)

### Reference Topics

The following concepts are closely related to CSS animations:

```text
CSS Transitions
CSS Transforms
CSS Timing Functions
CSS Pseudo-Classes
CSS Opacity
CSS Accessibility
```

> 💡 **Tip:** MDN is a useful practical reference for checking CSS animation syntax, browser behavior, and individual animation properties.

> 💡 **Remember:** Use official specifications and documentation when you need precise details about CSS animation behavior.

---

## Quick Revision

### What Are CSS Animations?

CSS animations allow CSS properties to change automatically over time using defined animation stages.

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

### Core Structure

```text
@keyframes
    ↓
Defines animation stages

animation
    ↓
Controls how the animation runs
```

### Main Animation Properties

| Property | Purpose |
| --- | --- |
| `animation-name` | Specifies the `@keyframes` animation |
| `animation-duration` | Defines the duration of one cycle |
| `animation-timing-function` | Controls the speed pattern |
| `animation-delay` | Delays the start |
| `animation-iteration-count` | Defines how many times it runs |
| `animation-direction` | Controls playback direction |
| `animation-fill-mode` | Controls styles before/after animation |
| `animation-play-state` | Pauses or resumes the animation |
| `animation` | Shorthand for animation properties |

### `@keyframes`

`@keyframes` defines the stages of an animation.

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Multiple stages can be created with percentages:

```css
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

### Animation Duration

```css
animation-duration: 2s;
```

Controls how long one animation cycle takes.

```text
1s = 1000ms
```

### Timing Functions

```text
ease
linear
ease-in
ease-out
ease-in-out
```

```text
linear
    ↓
Constant speed

ease-in
    ↓
Slow → Fast

ease-out
    ↓
Fast → Slow

ease-in-out
    ↓
Slow → Fast → Slow
```

### Animation Delay

```css
animation-delay: 0.5s;
```

Controls how long the browser waits before starting the animation.

A negative delay can make an animation behave as if it has already progressed along its timeline.

### Iteration Count

```css
animation-iteration-count: 3;
```

Runs the animation three times.

For continuous repetition:

```css
animation-iteration-count: infinite;
```

### Animation Direction

```text
normal
    ↓
Forward every iteration

reverse
    ↓
Backward every iteration

alternate
    ↓
Forward → Backward

alternate-reverse
    ↓
Backward → Forward
```

### Animation Fill Mode

```text
none
    ↓
No keyframe styles before/after

forwards
    ↓
Keep final keyframe

backwards
    ↓
Apply starting keyframe during delay

both
    ↓
Backwards + Forwards
```

### Animation Play State

```css
animation-play-state: running;
```

Animation continues to run.

```css
animation-play-state: paused;
```

Animation pauses at its current position.

### Animation Shorthand

Instead of:

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-timing-function: ease;
}
```

Use:

```css
.box {
    animation: move 2s ease;
}
```

A more complete example:

```css
.box {
    animation: move 2s ease 0s infinite alternate;
}
```

### Multiple Animations

Multiple animations are separated by commas.

```css
.box {
    animation:
        move 2s ease,
        fade 1s linear;
}
```

Each animation can have its own duration, timing function, delay, and iteration count.

### Animations with Transform

Common transform functions include:

```text
translate()
translateX()
translateY()
scale()
rotate()
```

Example:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

### Animations with Colors

Common color properties include:

```text
color
background-color
border-color
```

Example:

```css
@keyframes colorChange {
    from {
        background-color: steelblue;
    }

    to {
        background-color: darkblue;
    }
}
```

### Animations with Opacity

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

```text
opacity: 0
    ↓
Transparent

opacity: 1
    ↓
Fully visible
```

### Common Animation Patterns

```text
Fade In
    ↓
opacity: 0 → 1

Fade Out
    ↓
opacity: 1 → 0

Slide
    ↓
translateX() / translateY()

Scale
    ↓
scale()

Rotation
    ↓
rotate()

Pulse
    ↓
Repeated scale/opacity change

Loader
    ↓
rotate() + infinite
```

### CSS Animation vs CSS Transition

```text
Transition
    ↓
Usually handles a change between states
    ↓
Example: Normal → Hover

Animation
    ↓
Uses @keyframes
    ↓
Can have multiple stages
    ↓
Can start automatically
    ↓
Can repeat
    ↓
Can change direction
```

### Accessibility

Animations should consider users who prefer reduced motion.

```css
@media (prefers-reduced-motion: reduce) {
    .box {
        animation: none;
    }
}
```

### Final Revision

```text
CSS Animations
    ↓
@keyframes
    ↓
Animation stages
    ↓
animation-name
    ↓
animation-duration
    ↓
animation-timing-function
    ↓
animation-delay
    ↓
animation-iteration-count
    ↓
animation-direction
    ↓
animation-fill-mode
    ↓
animation-play-state
    ↓
animation shorthand
```

> 💡 **Remember:** `@keyframes` defines **what happens**, while the animation properties control **how it happens**.

> 💡 **Quick Interview Point:** CSS animations are especially useful for multi-stage, automatic, or repeating visual effects, while transitions are generally used for smooth changes between states.

---

## Best Practices

Following good practices makes CSS animations easier to understand, maintain, and use effectively.

### 1. Keep Animations Purposeful

Animations should have a clear purpose.

Good uses include:

- Providing visual feedback
- Showing changes in state
- Indicating loading activity
- Guiding user attention
- Improving the understanding of interface changes

Avoid adding animations simply because movement is possible.

```css
.button {
    animation: pulse 1s ease-in-out infinite;
}
```

If the animation does not provide useful information or improve the interface, it may be unnecessary.

### 2. Prefer Simple Animations

Simple animations are usually easier to maintain and understand.

For example:

```css
.card {
    animation: fadeIn 0.5s ease;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Start with simple effects before combining multiple properties.

### 3. Use Descriptive Animation Names

Use names that clearly describe the purpose of an animation.

Good:

```css
@keyframes fadeIn {
    /* ... */
}

@keyframes slideUp {
    /* ... */
}

@keyframes spin {
    /* ... */
}
```

Avoid unclear names:

```css
@keyframes animation1 {
    /* ... */
}

@keyframes test {
    /* ... */
}
```

Descriptive names make the CSS easier to understand.

### 4. Choose Appropriate Durations

Animation duration should match the purpose and size of the effect.

For example:

```css
.button {
    animation-duration: 0.2s;
}
```

A larger entrance effect might use:

```css
.card {
    animation-duration: 0.6s;
}
```

Avoid making small interface interactions unnecessarily slow.

### 5. Choose the Right Timing Function

Select a timing function based on the desired movement.

```text
linear
    ↓
Constant speed

ease-out
    ↓
Fast → Slow

ease-in
    ↓
Slow → Fast

ease-in-out
    ↓
Slow → Fast → Slow
```

For example:

```css
.card {
    animation: slideIn 0.6s ease-out;
}
```

### 6. Prefer `transform` for Movement

For many movement effects, use `transform` rather than changing layout-related properties.

For example:

```css
@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

Common transform functions include:

```css
translate()
translateX()
translateY()
scale()
rotate()
```

### 7. Combine Transform and Opacity Carefully

A common and effective entrance pattern is:

```css
.card {
    animation: entrance 0.6s ease-out;
}

@keyframes entrance {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

This creates movement and visibility changes together without requiring excessive effects.

### 8. Avoid Excessive Animation

Too much movement can make an interface distracting.

Avoid unnecessarily animating many elements simultaneously:

```text
Everything moves
      ↓
Visual noise
      ↓
Difficult to focus
```

Instead, animate the elements that need attention or feedback.

### 9. Use `animation-iteration-count` Carefully

Use finite iterations when an effect should happen a specific number of times.

```css
.notification {
    animation: pulse 1s ease 0s 2;
}
```

Use `infinite` only when continuous animation is actually necessary.

```css
.loader {
    animation: spin 1s linear infinite;
}
```

### 10. Use `animation-delay` Carefully

Delays can create useful staggered effects:

```css
.card:nth-child(1) {
    animation-delay: 0s;
}

.card:nth-child(2) {
    animation-delay: 0.2s;
}

.card:nth-child(3) {
    animation-delay: 0.4s;
}
```

However, excessive delays can make an interface feel slow.

### 11. Use `animation-fill-mode` When Needed

If an element should remain in its final animated state, use:

```css
animation-fill-mode: forwards;
```

For example:

```css
.card {
    animation: fadeIn 0.6s ease forwards;
}
```

Do not use fill modes unnecessarily when the default behavior is sufficient.

### 12. Consider Reduced Motion

Some users prefer reduced motion.

Use the `prefers-reduced-motion` media feature to reduce or disable non-essential animations.

```css
.card {
    animation: slideIn 0.6s ease-out;
}

@media (prefers-reduced-motion: reduce) {
    .card {
        animation: none;
    }
}
```

This can make animated interfaces more comfortable and accessible.

### 13. Keep Animation Code Readable

For simple animations, a concise declaration can be useful:

```css
.box {
    animation: move 1s ease-out;
}
```

For more complex animations, individual properties may be easier to understand:

```css
.box {
    animation-name: move;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    animation-iteration-count: 2;
}
```

Choose the style that makes the code easiest to maintain.

### 14. Avoid Conflicting Animations

Be careful when multiple animations modify the same property.

For example:

```css
.box {
    animation:
        move 2s ease,
        anotherMove 2s ease;
}
```

If both animations control the same property, their effects can conflict.

Prefer assigning different responsibilities to different animations when possible.

### 15. Test Animations at Different Speeds

An animation that looks good at one speed may not work well at another.

Test:

```text
Fast
 ↓
Normal
 ↓
Slow
```

Check whether the animation remains understandable and comfortable.

### 16. Test Different Screen Sizes

Animations should work correctly across different screen sizes and layouts.

Pay attention to:

- Movement distance
- Element visibility
- Overflow
- Responsive layouts
- Mobile interactions

### 17. Use Animations to Communicate State

Animation can provide useful feedback when something changes.

For example:

```text
Action
  ↓
Animation
  ↓
Visual feedback
  ↓
User understands the change
```

The animation should support the interaction rather than distract from it.

### 18. Avoid Animating Everything

Not every CSS property needs animation.

For example, an interface does not need every heading, paragraph, button, and card to animate simultaneously.

Use animation selectively.

### Best Practice Checklist

```text
⬜ Give animations a clear purpose
⬜ Keep animations simple
⬜ Use descriptive animation names
⬜ Choose appropriate durations
⬜ Choose suitable timing functions
⬜ Prefer transform for movement
⬜ Combine transform and opacity carefully
⬜ Avoid excessive movement
⬜ Use infinite animations only when necessary
⬜ Use delays carefully
⬜ Use fill modes when needed
⬜ Support reduced motion
⬜ Keep animation code readable
⬜ Avoid conflicting animations
⬜ Test different animation speeds
⬜ Test different screen sizes
⬜ Use animation to communicate state
⬜ Avoid animating everything
```

> 💡 **Tip:** The best animation is usually the one that improves the interface without making the user consciously think about the animation itself.

> 💡 **Remember:** Good CSS animation is not about using more effects. It is about using the right effect at the right time for the right purpose.

---

## Common Mistakes

Avoiding common mistakes helps make CSS animations more predictable, readable, accessible, and easier to maintain.

### 1. Forgetting `@keyframes`

Defining an animation name without defining the corresponding `@keyframes` rule will not create the intended animation.

Incorrect:

```css
.box {
    animation: move 2s;
}
```

Correct:

```css
.box {
    animation: move 2s;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

### 2. Using a Different Animation Name

The name used in `animation-name` must match the intended `@keyframes` name.

Incorrect:

```css
.box {
    animation-name: slideIn;
}

@keyframes slide {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Correct:

```css
.box {
    animation-name: slideIn;
}

@keyframes slideIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

### 3. Forgetting the Animation Duration

If no duration is specified, the animation does not have a useful time interval in which to run.

Incorrect:

```css
.box {
    animation-name: move;
}
```

Correct:

```css
.box {
    animation-name: move;
    animation-duration: 1s;
}
```

Or:

```css
.box {
    animation: move 1s;
}
```

### 4. Using an Excessive Duration

Animations that take too long can make an interface feel slow.

For example:

```css
.button {
    animation: effect 10s;
}
```

A small interface effect usually does not need such a long duration.

Choose a duration appropriate for the purpose of the animation.

### 5. Using `infinite` Unnecessarily

Not every animation should repeat forever.

Avoid:

```css
.card {
    animation: bounce 1s ease infinite;
}
```

if the effect only needs to happen when the card appears.

Use a finite iteration count when appropriate:

```css
.card {
    animation: bounce 1s ease 0s 2;
}
```

### 6. Overusing Animations

Animating every element can make a page distracting.

Avoid creating unnecessary movement on:

```text
Headings
Paragraphs
Buttons
Cards
Images
Navigation
Backgrounds
```

at the same time.

Use animation where it provides useful feedback or communication.

### 7. Forgetting `animation-fill-mode`

An entrance animation may appear to work and then return to its original styles after completing.

For example:

```css
.card {
    animation: fadeIn 0.6s ease;
}
```

If the final animated state needs to remain, use:

```css
.card {
    animation: fadeIn 0.6s ease forwards;
}
```

### 8. Confusing Delay with Duration

These properties have different purposes.

```css
.box {
    animation-duration: 2s;
    animation-delay: 1s;
}
```

Here:

```text
2s
 ↓
How long the animation runs

1s
 ↓
How long it waits before starting
```

Changing the delay does not change the duration of the animation itself.

### 9. Confusing Iteration Count with Duration

These properties also control different things.

```css
.box {
    animation-duration: 2s;
    animation-iteration-count: 3;
}
```

Here:

```text
2s
 ↓
One cycle takes 2 seconds

3
 ↓
The cycle runs 3 times
```

The total active animation time is therefore based on both values.

### 10. Using the Wrong Timing Function

Using `linear` for every animation can make some interface movements feel unnatural.

For example:

```css
.card {
    animation: slideIn 0.6s linear;
}
```

A different timing function may be more appropriate:

```css
.card {
    animation: slideIn 0.6s ease-out;
}
```

Choose timing functions according to the desired movement.

### 11. Forgetting `animation-direction`

When an animation should move back and forth, repeatedly playing it in the normal direction may not produce the intended effect.

For example:

```css
.box {
    animation: move 1s ease infinite alternate;
}
```

The `alternate` direction allows the animation to move forward and backward.

### 12. Conflicting Multiple Animations

Multiple animations can conflict when they modify the same property.

For example:

```css
.box {
    animation:
        moveLeft 2s,
        moveRight 2s;
}
```

If both animations attempt to control the same `transform` property, the result may not be what you expect.

Prefer separating responsibilities when possible.

### 13. Overusing Transform Functions

Combining too many transformations can make an animation difficult to understand.

For example:

```css
transform:
    translateX(100px)
    translateY(50px)
    rotate(180deg)
    scale(1.5);
```

Complex transformations are sometimes useful, but simpler animations are generally easier to maintain.

### 14. Forgetting Reduced Motion

Some users prefer reduced motion.

Avoid providing animations without considering accessibility.

A reduced-motion preference can be handled using:

```css
@media (prefers-reduced-motion: reduce) {
    .box {
        animation: none;
    }
}
```

### 15. Using Animation for Essential Information Only

Important information should not depend entirely on animation.

For example, do not communicate an important status only through movement or color changes.

Provide understandable content as well:

```html
<p>Upload complete</p>
```

The animation can provide additional feedback rather than being the only source of information.

### 16. Ignoring Mobile Devices

Animations should also be tested on smaller screens and touch devices.

Check for:

```text
Unexpected movement
Overflow
Performance issues
Difficult interactions
Excessive motion
```

### 17. Using Too Many Simultaneous Effects

Combining:

```text
Movement
+
Rotation
+
Scaling
+
Color changes
+
Opacity changes
```

can sometimes make an animation unnecessarily complicated.

Use only the effects that support the intended result.

### 18. Forgetting to Test the Final State

Always check what happens after the animation finishes.

For example:

```css
.box {
    animation: slideIn 1s ease;
}
```

Ask:

```text
What does the element look like before animation?
What happens during animation?
What does it look like after animation?
```

If the final state should remain, consider:

```css
animation-fill-mode: forwards;
```

### Common Mistakes Checklist

```text
⬜ Forgetting @keyframes
⬜ Using the wrong animation name
⬜ Forgetting animation duration
⬜ Using excessive duration
⬜ Using infinite unnecessarily
⬜ Overusing animations
⬜ Forgetting animation-fill-mode
⬜ Confusing delay with duration
⬜ Confusing iteration count with duration
⬜ Using the wrong timing function
⬜ Forgetting animation direction
⬜ Creating conflicting animations
⬜ Overcomplicating transforms
⬜ Ignoring reduced-motion preferences
⬜ Making animation the only source of important information
⬜ Ignoring mobile devices
⬜ Using too many simultaneous effects
⬜ Forgetting to test the final state
```

> 💡 **Tip:** When an animation does not behave as expected, first check the animation name, `@keyframes`, duration, iteration count, and fill mode.

> 💡 **Remember:** Most CSS animation problems can be avoided by keeping animations purposeful, simple, accessible, and easy to understand.

---

## Interview Questions

### Basic Questions

#### 1. What are CSS animations?

CSS animations allow CSS properties to change automatically over time using `@keyframes` and animation properties.

Example:

```css
.box {
    animation: move 2s ease;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

#### 2. What is the purpose of `@keyframes`?

The `@keyframes` rule defines the stages of a CSS animation.

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

It describes how CSS properties change during the animation.

#### 3. What is `animation-name`?

`animation-name` specifies the name of the `@keyframes` animation that should be applied.

```css
.box {
    animation-name: fadeIn;
}
```

The corresponding rule is:

```css
@keyframes fadeIn {
    /* animation stages */
}
```

#### 4. What does `animation-duration` do?

`animation-duration` specifies how long one animation cycle takes.

```css
.box {
    animation-duration: 2s;
}
```

#### 5. What is `animation-timing-function`?

It controls the speed pattern of an animation.

Common values include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

#### 6. What does `animation-delay` do?

It specifies how long the browser waits before starting an animation.

```css
.box {
    animation-delay: 1s;
}
```

#### 7. What is `animation-iteration-count`?

It specifies how many times an animation should run.

```css
.box {
    animation-iteration-count: 3;
}
```

For continuous repetition:

```css
.box {
    animation-iteration-count: infinite;
}
```

#### 8. What is `animation-direction`?

It controls the direction in which animation iterations are played.

The main values are:

```text
normal
reverse
alternate
alternate-reverse
```

#### 9. What does `animation-fill-mode` do?

It controls which animation keyframe styles are applied before and after the animation.

Common values include:

```text
none
forwards
backwards
both
```

#### 10. What is `animation-play-state`?

It controls whether an animation is running or paused.

```css
.box {
    animation-play-state: paused;
}
```

To resume:

```css
.box {
    animation-play-state: running;
}
```

### Intermediate Questions

#### 11. What is the difference between `animation` and `@keyframes`?

`@keyframes` defines the animation stages.

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

The `animation` property applies and controls those keyframes.

```css
.box {
    animation: move 2s ease;
}
```

In short:

```text
@keyframes
    ↓
What happens?

animation
    ↓
How it runs?
```

#### 12. What is the difference between `animation-duration` and `animation-delay`?

`animation-duration` controls how long the animation runs.

`animation-delay` controls how long the browser waits before starting it.

```css
.box {
    animation-duration: 2s;
    animation-delay: 1s;
}
```

```text
1s
 ↓
Wait

2s
 ↓
Animation runs
```

#### 13. What is the difference between `animation-iteration-count` and `animation-duration`?

`animation-duration` controls the length of one cycle.

`animation-iteration-count` controls how many cycles are played.

```css
.box {
    animation-duration: 2s;
    animation-iteration-count: 3;
}
```

The animation has three cycles, with each cycle taking two seconds.

#### 14. What does `animation-direction: alternate` do?

It makes successive animation iterations alternate between forward and reverse directions.

```css
.box {
    animation: move 1s ease infinite alternate;
}
```

The sequence is:

```text
Forward
   ↓
Backward
   ↓
Forward
   ↓
Backward
```

#### 15. What is `animation-fill-mode: forwards`?

It causes the element to retain the styles from the final keyframe after the animation finishes.

```css
.box {
    animation: move 1s ease forwards;
}
```

#### 16. What does `animation-play-state: paused` do?

It pauses an animation at its current position.

```css
.box {
    animation-play-state: paused;
}
```

When changed to:

```css
animation-play-state: running;
```

the animation continues from its paused position.

#### 17. Can multiple animations run on one element?

Yes.

They can be separated using commas.

```css
.box {
    animation:
        move 2s ease,
        fade 1s linear;
}
```

#### 18. Can CSS animations use `transform`?

Yes.

Common transform functions include:

```css
translate()
translateX()
translateY()
scale()
rotate()
```

Example:

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

#### 19. Can colors be animated with CSS?

Yes.

Common properties include:

```css
color
background-color
border-color
```

Example:

```css
@keyframes colorChange {
    from {
        background-color: steelblue;
    }

    to {
        background-color: darkblue;
    }
}
```

#### 20. Can opacity be animated?

Yes.

For example:

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

This creates a fade-in effect.

### Common Interview Comparison Questions

#### 21. CSS Animation vs CSS Transition

| CSS Animation | CSS Transition |
| --- | --- |
| Uses `@keyframes` | Usually works between two states |
| Can have multiple stages | Usually handles a state change |
| Can start automatically | Usually triggered by a property change |
| Can repeat | Does not repeat automatically |
| Supports animation direction | Does not have animation direction |
| Supports iteration count | Does not have iteration count |

Example transition:

```css
.button {
    transition: transform 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

Example animation:

```css
.box {
    animation: move 2s ease infinite;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

#### 22. Why is `transform` commonly used for animations?

`transform` is commonly used for visual movement, scaling, and rotation without changing the normal layout position of surrounding elements.

Example:

```css
@keyframes slide {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100px);
    }
}
```

#### 23. How can you create a continuously rotating loader?

Use `rotate()` together with `animation-iteration-count: infinite`.

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

#### 24. How can you pause an animation on hover?

Use `animation-play-state`.

```css
.box {
    animation: move 2s ease infinite alternate;
}

.box:hover {
    animation-play-state: paused;
}
```

#### 25. How can you create a staggered animation?

Use different `animation-delay` values.

```css
.item:nth-child(1) {
    animation-delay: 0s;
}

.item:nth-child(2) {
    animation-delay: 0.2s;
}

.item:nth-child(3) {
    animation-delay: 0.4s;
}
```

Each element starts at a different time.

### Accessibility Question

#### 26. How can CSS animations respect reduced-motion preferences?

Use the `prefers-reduced-motion` media feature.

```css
@media (prefers-reduced-motion: reduce) {
    .box {
        animation: none;
    }
}
```

This allows animations to be reduced or disabled for users who prefer less motion.

### Quick Interview Revision

```text
@keyframes
    → Defines animation stages

animation-name
    → Selects the keyframes

animation-duration
    → Controls cycle duration

animation-timing-function
    → Controls speed pattern

animation-delay
    → Delays the start

animation-iteration-count
    → Controls repetitions

animation-direction
    → Controls playback direction

animation-fill-mode
    → Controls styles before/after animation

animation-play-state
    → Pauses/resumes animation

animation
    → Shorthand property
```

> 💡 **Interview Tip:** When explaining CSS animations, start with the relationship between `@keyframes` and `animation`, then explain the individual animation properties.

> 💡 **Remember:** A strong answer should explain not only what a property does, but also when and why you would use it.

---

## Practice Exercises

The following exercises are designed to practice the CSS animation concepts covered in this chapter.

### Exercise 1: Fade-In Animation

Create a `<div>` element and make it fade in when the page loads.

Requirements:

- Start with `opacity: 0`.
- End with `opacity: 1`.
- Use `@keyframes`.
- Set the animation duration to `1s`.

Expected concepts:

```text
@keyframes
animation-name
animation-duration
opacity
```

---

### Exercise 2: Slide-In Animation

Create a card that slides in from the left.

Requirements:

- Start `50px` to the left.
- End at its normal position.
- Start with `opacity: 0`.
- End with `opacity: 1`.
- Use `transform: translateX()`.

Expected concepts:

```text
@keyframes
transform
translateX()
opacity
```

---

### Exercise 3: Rotating Loader

Create a circular loading indicator.

Requirements:

- Create a circular element.
- Use `transform: rotate()`.
- Make it rotate continuously.
- Use `linear`.
- Use `infinite`.

Expected concepts:

```text
animation-duration
animation-timing-function
animation-iteration-count
transform
rotate()
```

---

### Exercise 4: Bouncing Box

Create a box that repeatedly moves up and down.

Requirements:

- Use `translateY()`.
- Use at least three keyframe stages.
- Make the animation repeat continuously.
- Use `ease-in-out`.

Example structure:

```css
@keyframes bounce {
    0% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-40px);
    }

    100% {
        transform: translateY(0);
    }
}
```

---

### Exercise 5: Color Animation

Create an element whose background color changes over time.

Requirements:

- Start with one color.
- Change to another color.
- Use at least three keyframe stages.
- Repeat the animation.

Expected concepts:

```text
background-color
@keyframes
percentage keyframes
animation-iteration-count
```

---

### Exercise 6: Scale Animation

Create a button that continuously grows and shrinks.

Requirements:

- Use `transform: scale()`.
- Use `animation-direction: alternate`.
- Use `animation-iteration-count: infinite`.

Example:

```css
.button {
    animation: scaleButton 1s ease-in-out infinite alternate;
}

@keyframes scaleButton {
    from {
        transform: scale(1);
    }

    to {
        transform: scale(1.1);
    }
}
```

---

### Exercise 7: Staggered Cards

Create three cards that appear one after another.

Requirements:

- Use the same animation for all cards.
- Give each card a different `animation-delay`.
- Use `opacity`.
- Use `translateY()`.

Expected behavior:

```text
Card 1
   ↓
Card 2
   ↓
Card 3
```

---

### Exercise 8: Pause Animation on Hover

Create a continuously moving element.

Requirements:

- Use `animation-iteration-count: infinite`.
- Use `animation-play-state`.
- Pause the animation when the user hovers over the element.
- Resume the animation when the pointer leaves.

Example:

```css
.box {
    animation: move 2s ease-in-out infinite alternate;
}

.box:hover {
    animation-play-state: paused;
}
```

---

### Exercise 9: Multiple Animations

Create an element that:

- Moves horizontally.
- Changes its opacity.
- Changes its background color.

Use separate animations for the different effects.

Example structure:

```css
.box {
    animation:
        move 2s ease,
        fade 2s ease,
        colorChange 2s ease;
}
```

Create separate `@keyframes` rules for each animation.

---

### Exercise 10: Entrance Animation

Create a complete card entrance effect.

Requirements:

- Start transparent.
- Start slightly below its final position.
- Start slightly smaller.
- End fully visible.
- End at its normal position.
- End at its normal scale.
- Use `animation-fill-mode: forwards`.

Expected concepts:

```text
opacity
transform
translateY()
scale()
animation-fill-mode
forwards
```

---

### Exercise 11: Delayed Animation

Create three elements that start their animations at different times.

Use:

```css
animation-delay
```

Suggested delays:

```text
Element 1 → 0s
Element 2 → 0.3s
Element 3 → 0.6s
```

---

### Exercise 12: Reverse Animation

Create an animation and play it in reverse.

Use:

```css
animation-direction: reverse;
```

Then experiment with:

```css
animation-direction: alternate;
```

and:

```css
animation-direction: alternate-reverse;
```

Observe the difference between the three values.

---

### Exercise 13: Animation Fill Mode

Create an element that moves from left to right.

Requirements:

- Give the animation a duration of `1s`.
- Use `animation-fill-mode: forwards`.
- Check the element's position after the animation finishes.
- Remove `forwards` and compare the result.

---

### Exercise 14: Animation Timing Functions

Create the same animation several times and compare:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

For example:

```css
.box {
    animation: move 2s ease;
}
```

Change only the timing function and observe how the movement changes.

---

### Exercise 15: Reduced Motion

Create an animated card and add support for users who prefer reduced motion.

Use:

```css
@media (prefers-reduced-motion: reduce) {
    .card {
        animation: none;
    }
}
```

Verify that the animation is disabled when reduced motion is requested.

---

### Mini Project: Animated Notification

Create a notification component using several CSS animation concepts.

Requirements:

```text
Notification
    ↓
Fade in
    +
Slide up
    +
Remain in final position
    +
Button pulse
```

Suggested structure:

```html
<div class="notification">
    <h2>Success!</h2>
    <p>Your changes were saved.</p>
    <button>Continue</button>
</div>
```

Suggested concepts:

```text
@keyframes
animation
animation-duration
animation-timing-function
animation-fill-mode
opacity
transform
animation-delay
multiple animations
```

### Challenge

Create a loading screen that contains:

```text
Loading...
    +
Rotating loader
    +
Animated dots
    +
Fade-in message
```

Try to implement the complete effect using CSS animations without JavaScript.

### Practice Checklist

```text
⬜ Fade-in animation
⬜ Slide-in animation
⬜ Rotating loader
⬜ Bouncing box
⬜ Color animation
⬜ Scale animation
⬜ Staggered cards
⬜ Pause on hover
⬜ Multiple animations
⬜ Entrance animation
⬜ Delayed animations
⬜ Reverse animation
⬜ Fill-mode exercise
⬜ Timing-function comparison
⬜ Reduced-motion support
⬜ Animated notification mini project
⬜ Loading-screen challenge
```

> 💡 **Tip:** Try to solve these exercises without looking at the previous examples first. After completing an exercise, compare your solution with the concepts covered in this chapter.

> 💡 **Remember:** The goal of these exercises is not just to memorize animation properties, but to understand how the properties work together.