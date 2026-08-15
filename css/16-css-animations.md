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