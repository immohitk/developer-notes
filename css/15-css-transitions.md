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

---

## Why Are CSS Transitions Important?

CSS transitions are important because they make changes between CSS states smooth and visually understandable instead of happening instantly.

Without transitions, interactive elements can feel abrupt.

For example:

```css
.button {
    background-color: steelblue;
}

.button:hover {
    background-color: darkblue;
}
```

The color changes immediately when the user hovers over the button.

With a transition:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The color changes gradually, creating a smoother interaction.

### 1. Improve User Experience

Smooth transitions help users understand that an element has changed state.

For example:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The gradual color change provides visual feedback when the user interacts with the button.

### 2. Make Interfaces Feel More Responsive

Transitions can make interactions feel more natural.

For example:

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

The card smoothly moves upward instead of jumping to its new position.

### 3. Create Smooth Hover Effects

Transitions are frequently used with the `:hover` pseudo-class.

```css
.link {
    color: black;
    transition: color 0.3s ease;
}

.link:hover {
    color: steelblue;
}
```

This creates a smooth color change when the pointer moves over the link.

### 4. Improve Visual Feedback

Transitions can provide clear feedback for actions such as:

- Hovering over a button
- Focusing on an input
- Opening a menu
- Expanding a card
- Changing a color
- Showing or hiding an element

For example:

```css
input {
    border: 2px solid gray;
    transition: border-color 0.3s ease;
}

input:focus {
    border-color: steelblue;
}
```

The border color changes smoothly when the input receives focus.

### 5. Enhance Animations and Transforms

Transitions work especially well with CSS transforms.

```css
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
}
```

The card smoothly grows when hovered.

### 6. Make UI Changes Less Abrupt

Instant changes can sometimes make an interface feel harsh or disconnected.

A transition can make the same change feel more natural:

```css
.box {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.box:hover {
    opacity: 0.5;
}
```

The opacity gradually changes instead of switching immediately.

### 7. Create Professional-Looking Interfaces

Well-designed transitions can make websites feel more polished.

They are commonly found in:

- Navigation menus
- Buttons
- Cards
- Forms
- Links
- Dropdowns
- Image galleries
- Modals
- Interactive components

> 💡 **Tip:** Transitions should support the user experience rather than distract from it. Subtle transitions are usually more effective than excessive movement.

> 💡 **Remember:** CSS transitions make state changes smoother, improve visual feedback, and help create responsive and polished interfaces.

---

## Transition Syntax

The `transition` property is used to control how a CSS property changes from one value to another.

A basic transition can be written like this:

```css
.box {
    transition: property duration;
}
```

For example:

```css
.box {
    background-color: steelblue;
    transition: background-color 0.3s;
}

.box:hover {
    background-color: darkblue;
}
```

Here:

```text
background-color → Property being transitioned
0.3s             → Duration of the transition
```

### Basic Syntax

The general syntax is:

```css
selector {
    transition: property duration;
}
```

For example:

```css
button {
    transition: background-color 0.5s;
}
```

This tells the browser to smoothly transition changes to `background-color` over `0.5` seconds.

### Complete Transition Syntax

The `transition` shorthand can include several values:

```css
selector {
    transition: property duration timing-function delay;
}
```

For example:

```css
button {
    transition: background-color 0.5s ease 0.2s;
}
```

The values represent:

```text
background-color → Property
0.5s             → Duration
ease             → Timing function
0.2s             → Delay
```

### Using `transition-property`

You can specify which CSS property should transition:

```css
.box {
    transition-property: background-color;
}
```

### Using `transition-duration`

You can specify how long the transition should take:

```css
.box {
    transition-duration: 0.5s;
}
```

### Using `transition-timing-function`

You can control the speed pattern of the transition:

```css
.box {
    transition-timing-function: ease;
}
```

### Using `transition-delay`

You can delay the beginning of the transition:

```css
.box {
    transition-delay: 0.2s;
}
```

These individual properties can also be combined using the `transition` shorthand:

```css
.box {
    transition: background-color 0.5s ease 0.2s;
}
```

### Example

```html
<button class="button">Hover Me</button>
```

```css
.button {
    background-color: steelblue;
    color: white;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The transition syntax tells the browser to smoothly change the `background-color` when the button enters or leaves the hover state.

> 💡 **Remember:** The basic transition syntax is `property duration`, while the complete shorthand can include `property`, `duration`, `timing-function`, and `delay`.

---

## Transition Property

The `transition-property` property specifies which CSS property or properties should transition smoothly when their values change.

For example:

```css
.box {
    transition-property: background-color;
    transition-duration: 0.3s;
}

.box:hover {
    background-color: darkblue;
}
```

Here, only the `background-color` property is transitioned.

### Syntax

The basic syntax is:

```css
selector {
    transition-property: property;
}
```

For example:

```css
.box {
    transition-property: width;
}
```

The transition duration can be specified separately:

```css
.box {
    transition-property: width;
    transition-duration: 0.5s;
}
```

### Transitioning Multiple Properties

Multiple properties can be specified by separating them with commas:

```css
.box {
    transition-property: width, height, background-color;
    transition-duration: 0.5s;
}
```

Now changes to `width`, `height`, and `background-color` can transition smoothly.

### Example

```html
<div class="box">Hover Me</div>
```

```css
.box {
    width: 150px;
    height: 100px;
    background-color: steelblue;

    transition-property: width, background-color;
    transition-duration: 0.5s;
}

.box:hover {
    width: 250px;
    background-color: darkblue;
}
```

When the user hovers over the box:

- `width` changes smoothly.
- `background-color` changes smoothly.
- `height` does not transition because it was not included in `transition-property`.

### Using `all`

The value `all` can be used to transition all properties that can be transitioned:

```css
.box {
    transition-property: all;
    transition-duration: 0.3s;
}
```

For example:

```css
.box {
    width: 150px;
    background-color: steelblue;
    transform: scale(1);

    transition-property: all;
    transition-duration: 0.3s;
}

.box:hover {
    width: 200px;
    background-color: darkblue;
    transform: scale(1.05);
}
```

All of the applicable changes can transition smoothly.

However, using `all` unnecessarily can make it less clear which properties are intended to transition.

### Using `none`

The `none` value means that no property should transition:

```css
.box {
    transition-property: none;
}
```

This can be useful when transitions need to be disabled.

### Common Values

| Value | Description |
| --- | --- |
| `none` | No properties are transitioned |
| `all` | All applicable properties are transitioned |
| `property` | A specific property is transitioned |
| `property1, property2` | Multiple specific properties are transitioned |

> 💡 **Tip:** When you know exactly which properties need a transition, specifying them explicitly can make your CSS clearer and easier to maintain.

> 💡 **Remember:** `transition-property` decides **what changes smoothly**, while `transition-duration` decides **how long the change takes**.

---

## Transition Duration

The `transition-duration` property specifies how long a transition should take to complete.

It controls the amount of time the browser takes to change a property from its starting value to its new value.

### Syntax

The basic syntax is:

```css
selector {
    transition-duration: time;
}
```

For example:

```css
.box {
    transition-duration: 0.5s;
}
```

Here, `0.5s` means the transition takes half a second to complete.

### Using Seconds

The duration can be specified using seconds (`s`):

```css
.box {
    transition-duration: 1s;
}
```

This creates a transition lasting one second.

Another example:

```css
.box {
    transition-duration: 0.3s;
}
```

This creates a transition lasting `0.3` seconds.

### Using Milliseconds

The duration can also be specified using milliseconds (`ms`):

```css
.box {
    transition-duration: 300ms;
}
```

`300ms` is equivalent to `0.3s`.

```text
1s    = 1000ms
0.5s  = 500ms
0.3s  = 300ms
0.1s  = 100ms
```

### Example

```html
<button class="button">Hover Me</button>
```

```css
.button {
    background-color: steelblue;
    transition-property: background-color;
    transition-duration: 0.5s;
}

.button:hover {
    background-color: darkblue;
}
```

When the button is hovered, the background color gradually changes over `0.5` seconds.

### Different Durations

Different transition durations create different visual effects.

```css
.box {
    transition-duration: 0.1s;
}
```

A very short duration creates a fast change.

```css
.box {
    transition-duration: 1s;
}
```

A longer duration creates a slower change.

```css
.box {
    transition-duration: 2s;
}
```

A very long duration makes the change noticeably slow.

### Transition Duration with Shorthand

The duration can be included directly in the `transition` shorthand:

```css
.box {
    transition: background-color 0.5s ease;
}
```

Here:

```text
background-color → Property
0.5s             → Duration
ease             → Timing function
```

### Multiple Transition Durations

When multiple properties are transitioned, multiple durations can be provided:

```css
.box {
    transition-property: width, background-color;
    transition-duration: 0.5s, 1s;
}
```

Here:

```text
width            → 0.5s
background-color → 1s
```

The values correspond to the properties in the same order.

### Duration of `0s`

A duration of `0s` means that the transition has no visible duration:

```css
.box {
    transition-duration: 0s;
}
```

The property change occurs immediately rather than gradually.

> 💡 **Tip:** Use shorter durations for small interface interactions and longer durations only when a slower visual effect is appropriate.

> 💡 **Remember:** `transition-duration` controls **how long the transition takes**, while `transition-property` controls **which property changes smoothly**.

---

## Transition Timing Function

The `transition-timing-function` property controls the **speed pattern** of a transition during its duration.

It determines how quickly the transition progresses at different points between the starting value and the ending value.

### Syntax

The basic syntax is:

```css
selector {
    transition-timing-function: value;
}
```

For example:

```css
.box {
    transition-property: width;
    transition-duration: 1s;
    transition-timing-function: ease;
}
```

The transition still takes `1s`, but the timing function controls how the change progresses during that time.

### `ease`

The `ease` value starts relatively slowly, speeds up, and then slows down toward the end.

```css
.box {
    transition: width 1s ease;
}
```

`ease` is commonly used for general interface interactions.

### `linear`

The `linear` value changes at a constant speed throughout the transition.

```css
.box {
    transition: width 1s linear;
}
```

The transition progresses evenly from start to finish.

### `ease-in`

The `ease-in` value starts slowly and becomes faster toward the end.

```css
.box {
    transition: width 1s ease-in;
}
```

### `ease-out`

The `ease-out` value starts faster and slows down toward the end.

```css
.box {
    transition: width 1s ease-out;
}
```

### `ease-in-out`

The `ease-in-out` value starts slowly, speeds up in the middle, and slows down again toward the end.

```css
.box {
    transition: width 1s ease-in-out;
}
```

### Timing Function Comparison

```text
linear       → Constant speed
ease         → Slow → Fast → Slow
ease-in      → Slow → Fast
ease-out     → Fast → Slow
ease-in-out  → Slow → Fast → Slow
```

### Example

```html
<button class="button">Hover Me</button>
```

```css
.button {
    width: 120px;
    transition-property: width;
    transition-duration: 1s;
    transition-timing-function: ease-out;
}

.button:hover {
    width: 250px;
}
```

When the button is hovered, its width changes over one second using the `ease-out` speed pattern.

### Using the Shorthand

The timing function can be included in the `transition` shorthand:

```css
.button {
    transition: width 1s ease-out;
}
```

Here:

```text
width    → Property
1s       → Duration
ease-out → Timing function
```

### `cubic-bezier()`

CSS also provides the `cubic-bezier()` function for creating custom timing functions.

```css
.box {
    transition: transform 1s cubic-bezier(0.4, 0, 0.2, 1);
}
```

This allows more precise control over the transition's speed pattern.

### `steps()`

The `steps()` function divides the transition into a specified number of discrete steps instead of producing a continuously smooth change.

```css
.box {
    transition: width 1s steps(5);
}
```

The transition progresses through five distinct steps.

> 💡 **Tip:** `ease`, `ease-in`, `ease-out`, and `ease-in-out` are useful for common interface effects, while `cubic-bezier()` and `steps()` provide more specialized control.

> 💡 **Remember:** `transition-duration` controls **how long** the transition takes, while `transition-timing-function` controls **how the speed changes during that time**.

---

## Transition Delay

The `transition-delay` property specifies how long the browser should wait before starting a transition.

It is useful when you want a transition to begin after a short pause.

### Syntax

The basic syntax is:

```css
selector {
    transition-delay: time;
}
```

For example:

```css
.box {
    transition-property: background-color;
    transition-duration: 0.5s;
    transition-delay: 0.2s;
}
```

Here:

```text
0.5s → Transition duration
0.2s → Delay before the transition starts
```

### Using Seconds

The delay can be specified in seconds:

```css
.box {
    transition-delay: 0.5s;
}
```

The transition waits for `0.5` seconds before starting.

### Using Milliseconds

The delay can also be specified in milliseconds:

```css
.box {
    transition-delay: 200ms;
}
```

`200ms` is equivalent to `0.2s`.

```text
1s    = 1000ms
0.5s  = 500ms
0.2s  = 200ms
0.1s  = 100ms
```

### Example

```html
<button class="button">Hover Me</button>
```

```css
.button {
    background-color: steelblue;
    transition: background-color 0.5s ease;
    transition-delay: 0.3s;
}

.button:hover {
    background-color: darkblue;
}
```

When the user hovers over the button:

1. The browser waits `0.3s`.
2. The background color transition begins.
3. The color change takes `0.5s`.

### Delay with the Transition Shorthand

The delay can be included in the `transition` shorthand:

```css
.button {
    transition: background-color 0.5s ease 0.3s;
}
```

The values represent:

```text
background-color → Property
0.5s             → Duration
ease             → Timing function
0.3s             → Delay
```

### Multiple Transition Delays

When multiple properties are transitioned, multiple delay values can be provided.

```css
.box {
    transition-property: width, background-color;
    transition-duration: 0.5s, 1s;
    transition-delay: 0s, 0.3s;
}
```

Here:

```text
width            → Duration: 0.5s → Delay: 0s
background-color → Duration: 1s   → Delay: 0.3s
```

The values correspond to the properties in the same order.

### Zero Delay

A delay of `0s` means the transition starts immediately:

```css
.box {
    transition-delay: 0s;
}
```

This is the default behavior when no delay is specified.

### Negative Delay

A negative delay can be used:

```css
.box {
    transition-delay: -0.2s;
}
```

A negative delay causes the transition to behave as though it had already been running for the specified amount of time when it begins.

This can create advanced transition effects, but it is less commonly needed in basic interface design.

> 💡 **Tip:** Small positive delays can be useful for creating sequential or staggered interface effects.

> 💡 **Remember:** `transition-delay` controls **when the transition starts**, while `transition-duration` controls **how long the transition takes**.

---

## Transition Shorthand

The `transition` property is a shorthand property that allows you to define multiple transition properties in a single declaration.

Instead of writing each transition property separately:

```css
.box {
    transition-property: background-color;
    transition-duration: 0.5s;
    transition-timing-function: ease;
    transition-delay: 0.2s;
}
```

You can combine them using the `transition` shorthand:

```css
.box {
    transition: background-color 0.5s ease 0.2s;
}
```

### Shorthand Syntax

The general syntax is:

```css
selector {
    transition: property duration timing-function delay;
}
```

For example:

```css
.box {
    transition: background-color 0.5s ease 0.2s;
}
```

The values represent:

```text
background-color → Transition property
0.5s             → Transition duration
ease             → Timing function
0.2s             → Transition delay
```

### Basic Shorthand

Only the property and duration are required for a simple transition:

```css
.box {
    transition: background-color 0.5s;
}
```

Here:

```text
background-color → Property
0.5s             → Duration
```

The timing function uses its default value when it is not specified.

### Adding a Timing Function

You can add a timing function:

```css
.box {
    transition: background-color 0.5s ease;
}
```

Here:

```text
background-color → Property
0.5s             → Duration
ease             → Timing function
```

### Adding a Delay

You can also specify a delay:

```css
.box {
    transition: background-color 0.5s ease 0.2s;
}
```

Here:

```text
background-color → Property
0.5s             → Duration
ease             → Timing function
0.2s             → Delay
```

### Example

```html
<button class="button">Hover Me</button>
```

```css
.button {
    background-color: steelblue;
    color: white;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The shorthand makes the CSS shorter while still providing the same transition behavior.

### Multiple Properties

Multiple transitions can be specified by separating them with commas:

```css
.box {
    transition:
        background-color 0.3s ease,
        transform 0.5s ease,
        width 0.4s ease;
}
```

Each transition controls a different property.

For example:

```css
.box:hover {
    background-color: darkblue;
    transform: scale(1.05);
    width: 200px;
}
```

The three properties transition according to their respective transition definitions.

### `all` with Shorthand

The `all` keyword can also be used:

```css
.box {
    transition: all 0.3s ease;
}
```

This allows all applicable transitioning properties to change smoothly.

However, explicitly specifying properties can make the intended behavior clearer:

```css
.box {
    transition: transform 0.3s ease, background-color 0.3s ease;
}
```

### Comparing Longhand and Shorthand

Longhand:

```css
.box {
    transition-property: transform;
    transition-duration: 0.3s;
    transition-timing-function: ease;
    transition-delay: 0s;
}
```

Shorthand:

```css
.box {
    transition: transform 0.3s ease;
}
```

Both describe the same basic transition behavior.

> 💡 **Tip:** The shorthand form is commonly preferred when you want to keep transition declarations concise.

> 💡 **Remember:** The `transition` shorthand combines `transition-property`, `transition-duration`, `transition-timing-function`, and `transition-delay` into one declaration.

---

## Multiple Transitions

CSS allows you to apply transitions to multiple properties of an element.

When several CSS properties need to change smoothly, you can define multiple transitions by separating each transition with a comma.

### Syntax

The basic syntax is:

```css
selector {
    transition: property1 duration1,
                property2 duration2;
}
```

For example:

```css
.box {
    transition:
        width 0.5s ease,
        background-color 0.3s ease;
}
```

Here:

```text
width            → 0.5s
background-color → 0.3s
```

Each property has its own transition duration.

### Example

```html
<div class="box">Hover Me</div>
```

```css
.box {
    width: 150px;
    height: 100px;
    background-color: steelblue;

    transition:
        width 0.5s ease,
        background-color 0.3s ease;
}

.box:hover {
    width: 250px;
    background-color: darkblue;
}
```

When the user hovers over the box:

- The `width` changes smoothly over `0.5s`.
- The `background-color` changes smoothly over `0.3s`.

### Multiple Properties with Different Timing Functions

Each property can also have its own timing function.

```css
.box {
    transition:
        width 0.5s ease-in,
        background-color 0.3s ease-out,
        transform 0.6s linear;
}
```

Here:

```text
width            → 0.5s → ease-in
background-color → 0.3s → ease-out
transform        → 0.6s → linear
```

### Multiple Properties with Delays

Different transitions can also have different delays.

```css
.box {
    transition:
        width 0.5s ease 0s,
        background-color 0.5s ease 0.2s,
        transform 0.5s ease 0.4s;
}
```

Here:

```text
width            → Starts immediately
background-color → Starts after 0.2s
transform        → Starts after 0.4s
```

This can create a staggered visual effect.

### Using Longhand Properties

Multiple transitions can also be defined using the individual transition properties.

```css
.box {
    transition-property: width, background-color, transform;
    transition-duration: 0.5s, 0.3s, 0.6s;
    transition-timing-function: ease, ease-out, linear;
    transition-delay: 0s, 0.2s, 0.4s;
}
```

The values correspond to the properties in the same order.

```text
Property         Duration   Timing       Delay
------------------------------------------------
width            0.5s       ease         0s
background-color 0.3s       ease-out     0.2s
transform        0.6s       linear       0.4s
```

### Using Multiple Transitions with Transform

Multiple transitions are often used together with CSS transforms.

```css
.card {
    background-color: white;
    transform: translateY(0);

    transition:
        transform 0.3s ease,
        background-color 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    background-color: lightgray;
}
```

Both properties change smoothly when the card is hovered.

### Multiple Transitions with Different Durations

Different properties do not need to use the same duration.

```css
.button {
    transform: scale(1);
    background-color: steelblue;
    color: white;

    transition:
        transform 0.2s ease,
        background-color 0.4s ease,
        color 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
    background-color: darkblue;
    color: lightgray;
}
```

This allows each property to have its own transition behavior.

> 💡 **Tip:** Use multiple transitions when different properties need different durations, timing functions, or delays.

> 💡 **Remember:** Multiple transitions are separated by commas, and each transition describes how one property should change.

---

## Transitions with Hover

The `:hover` pseudo-class is commonly used with CSS transitions to create smooth interactive effects when the user moves the pointer over an element.

A transition defines how the property changes, while `:hover` defines the state in which the property changes.

### Basic Example

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

When the pointer moves over the button, the `background-color` changes smoothly.

When the pointer leaves the button, the color smoothly returns to its original value.

### Button Hover Effect

```html
<button class="button">Hover Me</button>
```

```css
.button {
    padding: 12px 24px;
    background-color: steelblue;
    color: white;
    border: none;
    cursor: pointer;

    transition:
        background-color 0.3s ease,
        transform 0.3s ease;
}

.button:hover {
    background-color: darkblue;
    transform: scale(1.05);
}
```

This example combines a color transition with a transform transition.

### Changing Text Color

Transitions can be used to smoothly change the color of links.

```css
.link {
    color: black;
    transition: color 0.3s ease;
}

.link:hover {
    color: steelblue;
}
```

### Changing Opacity

A hover transition can also change an element's opacity.

```css
.image {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.image:hover {
    opacity: 0.7;
}
```

The image gradually becomes more transparent when the pointer moves over it.

### Moving an Element

Transitions can be combined with transforms to create movement.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

The card smoothly moves upward when hovered.

### Combining Multiple Hover Effects

Several properties can transition at the same time.

```css
.card {
    background-color: white;
    transform: translateY(0);
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);

    transition:
        background-color 0.3s ease,
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    background-color: lightgray;
    transform: translateY(-8px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

The card changes multiple properties smoothly during the hover state.

### Hovering Over Images

Transitions are frequently used to create image zoom effects.

```css
.image-container {
    overflow: hidden;
}

.image {
    transition: transform 0.4s ease;
}

.image:hover {
    transform: scale(1.05);
}
```

The image gradually becomes larger when hovered.

### Hover Effects on Navigation Links

```css
.nav-link {
    color: black;
    text-decoration: none;
    transition: color 0.3s ease;
}

.nav-link:hover {
    color: steelblue;
}
```

This provides smooth visual feedback when the user moves the pointer over a navigation link.

### Important Point

The transition should normally be placed on the element's normal state rather than only on the `:hover` state.

Recommended:

```css
.button {
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

Avoid:

```css
.button:hover {
    transition: background-color 0.3s ease;
    background-color: darkblue;
}
```

Putting the transition only on `:hover` can cause the transition to behave differently when the pointer leaves the element.

> 💡 **Tip:** Put the `transition` declaration on the base element and use `:hover` only to define the changed values.

> 💡 **Remember:** `:hover` defines the interactive state, while `transition` controls how smoothly the element moves from one state to another.

---

## Transitions with Transform

CSS transitions can be combined with the `transform` property to create smooth movement, scaling, rotation, and other visual effects.

The `transform` property defines the transformation, while the `transition` property controls how smoothly that transformation happens.

### Basic Example

```css
.box {
    transform: scale(1);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.1);
}
```

When the user hovers over the box, it smoothly grows to `110%` of its original size.

### Translate with Transition

The `translate()` function can be combined with a transition to create smooth movement.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-10px);
}
```

The card smoothly moves upward by `10px` when hovered.

### Scale with Transition

The `scale()` function can create a smooth zoom effect.

```css
.image {
    transform: scale(1);
    transition: transform 0.4s ease;
}

.image:hover {
    transform: scale(1.05);
}
```

The image gradually becomes slightly larger when hovered.

### Rotate with Transition

The `rotate()` function can create a smooth rotation effect.

```css
.icon {
    transform: rotate(0deg);
    transition: transform 0.3s ease;
}

.icon:hover {
    transform: rotate(45deg);
}
```

The element smoothly rotates by `45deg`.

### Combining Transform Functions

Multiple transform functions can be used together.

```css
.card {
    transform: translateY(0) scale(1);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px) scale(1.05);
}
```

When hovered, the card:

1. Moves upward.
2. Becomes slightly larger.

Both changes happen smoothly because the `transform` property is transitioned.

### Transform with Multiple Properties

A transform transition can also be combined with other CSS property transitions.

```css
.card {
    background-color: white;
    transform: translateY(0);
    transition:
        transform 0.3s ease,
        background-color 0.3s ease;
}

.card:hover {
    background-color: lightgray;
    transform: translateY(-8px);
}
```

The card moves upward while its background color changes smoothly.

### Scale and Shadow Effect

A common card hover effect combines `scale()` with `box-shadow`.

```css
.card {
    transform: scale(1);
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: scale(1.03);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

This creates a subtle lifting effect.

### Transform Origin

The `transform-origin` property can be used to control the point around which a transformation occurs.

```css
.box {
    transform-origin: top left;
    transform: rotate(0deg);
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotate(15deg);
}
```

The box rotates around its top-left corner.

### Transitioning Transform Instead of Individual Transform Functions

The transition should target the `transform` property:

```css
.box {
    transition: transform 0.3s ease;
}
```

It should not be written as:

```css
.box {
    transition: scale 0.3s ease;
}
```

when the transformation is being defined through:

```css
.box:hover {
    transform: scale(1.1);
}
```

The transition is applied to the CSS property whose value changes.

### Practical Example

```html
<div class="card">
    <h2>CSS Transitions</h2>
    <p>Hover over this card.</p>
</div>
```

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;
    transform: translateY(0) scale(1);

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-8px) scale(1.03);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

This creates a smooth card interaction using both `translateY()` and `scale()`.

> 💡 **Tip:** `transform` and `transition` are commonly used together because transforms are efficient for creating smooth visual movement and interaction effects.

> 💡 **Remember:** `transform` defines **what visual transformation happens**, while `transition` defines **how smoothly the transformation happens**.

---

## Transitions with Colors

CSS transitions can be used to smoothly change color-related properties such as `color`, `background-color`, and `border-color`.

Instead of changing from one color to another immediately, the browser gradually changes the color over the specified transition duration.

### Background Color

The `background-color` property is commonly used with transitions.

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

When the user hovers over the button, the background color changes smoothly.

### Text Color

The `color` property can also be transitioned.

```css
.link {
    color: black;
    transition: color 0.3s ease;
}

.link:hover {
    color: steelblue;
}
```

The text color gradually changes when the user hovers over the link.

### Border Color

Transitions can be applied to `border-color`.

```css
.input {
    border: 2px solid gray;
    transition: border-color 0.3s ease;
}

.input:focus {
    border-color: steelblue;
}
```

When the input receives focus, the border color changes smoothly.

### Multiple Color Properties

Multiple color properties can be transitioned at the same time.

```css
.button {
    background-color: white;
    color: black;
    border-color: gray;

    transition:
        background-color 0.3s ease,
        color 0.3s ease,
        border-color 0.3s ease;
}

.button:hover {
    background-color: steelblue;
    color: white;
    border-color: steelblue;
}
```

Here, all three color properties transition smoothly.

### Using the `transition` Shorthand

The shorthand property can make color transitions more concise.

```css
.button {
    background-color: steelblue;
    color: white;

    transition:
        background-color 0.3s ease,
        color 0.3s ease;
}
```

### Color Transition with Hover

A common example is a navigation link:

```html
<a href="#" class="nav-link">Home</a>
```

```css
.nav-link {
    color: black;
    text-decoration: none;
    transition: color 0.3s ease;
}

.nav-link:hover {
    color: steelblue;
}
```

The link changes color smoothly when the pointer moves over it.

### Color Transition with Focus

Transitions can also provide smooth feedback when an element receives focus.

```css
input {
    border: 2px solid gray;
    outline: none;
    transition: border-color 0.3s ease;
}

input:focus {
    border-color: steelblue;
}
```

This is useful for form controls and other interactive elements.

### Color Transition with Buttons

```html
<button class="button">Submit</button>
```

```css
.button {
    background-color: steelblue;
    color: white;
    border: none;
    padding: 12px 24px;
    transition:
        background-color 0.3s ease,
        color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
    color: white;
}
```

The button's background color changes smoothly when hovered.

### Using Color Transitions with Other Effects

Color transitions can be combined with transforms and other properties.

```css
.card {
    background-color: white;
    transform: translateY(0);

    transition:
        background-color 0.3s ease,
        transform 0.3s ease;
}

.card:hover {
    background-color: lightgray;
    transform: translateY(-8px);
}
```

The card changes its background color while smoothly moving upward.

> 💡 **Tip:** Color transitions are useful for providing visual feedback without requiring complicated animations.

> 💡 **Remember:** Transition the specific color property that changes, such as `color`, `background-color`, or `border-color`.

---

## Transitions with Size

CSS transitions can be used to smoothly change the size of an element.

Common properties used for size transitions include:

- `width`
- `height`
- `max-width`
- `max-height`

The transition controls how smoothly the element changes from its original size to its new size.

### Changing Width

The `width` property can be transitioned to create a smooth horizontal size change.

```css
.box {
    width: 150px;
    transition: width 0.5s ease;
}

.box:hover {
    width: 250px;
}
```

When the user hovers over the box, its width gradually changes from `150px` to `250px`.

### Changing Height

The `height` property can also be transitioned.

```css
.box {
    height: 100px;
    transition: height 0.5s ease;
}

.box:hover {
    height: 200px;
}
```

The element smoothly grows vertically when hovered.

### Changing Width and Height Together

Both dimensions can be transitioned at the same time.

```css
.box {
    width: 150px;
    height: 100px;

    transition:
        width 0.5s ease,
        height 0.5s ease;
}

.box:hover {
    width: 250px;
    height: 200px;
}
```

When hovered, the element smoothly becomes both wider and taller.

### Using the Transition Shorthand

When the same duration and timing function are used, the shorthand can make the code shorter.

```css
.box {
    width: 150px;
    height: 100px;

    transition:
        width 0.5s ease,
        height 0.5s ease;
}
```

### Expanding a Button

A common use of size transitions is creating an expanding button.

```html
<button class="button">Learn More</button>
```

```css
.button {
    width: 120px;
    padding: 12px;
    transition: width 0.3s ease;
}

.button:hover {
    width: 180px;
}
```

The button smoothly becomes wider when the user hovers over it.

### Expanding a Card

Size transitions can also be used with cards.

```css
.card {
    width: 250px;
    padding: 20px;
    transition: width 0.4s ease;
}

.card:hover {
    width: 300px;
}
```

The card gradually expands when hovered.

### Size Transitions with Transform

For many visual scaling effects, `transform: scale()` is often preferable to changing `width` or `height`.

For example:

```css
.card {
    transform: scale(1);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
}
```

This visually enlarges the card without changing its layout dimensions in the same way as changing `width` or `height`.

### Width vs Scale

Changing `width`:

```css
.box {
    width: 150px;
    transition: width 0.3s ease;
}

.box:hover {
    width: 200px;
}
```

Using `scale()`:

```css
.box {
    transform: scale(1);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.1);
}
```

These approaches produce different results.

```text
width / height
    ↓
Changes the element's dimensions

transform: scale()
    ↓
Visually scales the element
```

### Practical Example

```html
<div class="card">
    <h2>CSS</h2>
    <p>Hover over this card.</p>
</div>
```

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;

    transition:
        width 0.4s ease,
        background-color 0.3s ease;
}

.card:hover {
    width: 300px;
    background-color: lightgray;
}
```

The card smoothly expands while its background color changes.

> 💡 **Tip:** Use size transitions when the actual dimensions of an element need to change. For simple visual zoom effects, `transform: scale()` is often a better choice.

> 💡 **Remember:** `width` and `height` transitions change an element's dimensions, while `transform: scale()` creates a visual scaling effect.

---

## Transitions with Position

CSS transitions can be used to create smooth movement when an element changes its position.

Position-related effects can be created using properties such as:

- `transform`
- `top`
- `right`
- `bottom`
- `left`
- `margin`

For most simple movement effects, `transform` is generally preferred.

### Moving with `transform`

The `translate()` functions can be used to move an element smoothly.

```css
.box {
    transform: translateX(0);
    transition: transform 0.5s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

When the user hovers over the box, it smoothly moves `50px` to the right.

### Moving Vertically

The `translateY()` function can be used for vertical movement.

```css
.box {
    transform: translateY(0);
    transition: transform 0.4s ease;
}

.box:hover {
    transform: translateY(-20px);
}
```

The box smoothly moves `20px` upward.

### Moving in Both Directions

The `translate()` function can change both horizontal and vertical position.

```css
.box {
    transform: translate(0, 0);
    transition: transform 0.5s ease;
}

.box:hover {
    transform: translate(30px, -20px);
}
```

The element moves:

```text
30px → Right
20px → Up
```

### Moving with `left`

Position properties can also be transitioned.

```css
.box {
    position: relative;
    left: 0;
    transition: left 0.5s ease;
}

.box:hover {
    left: 50px;
}
```

The element smoothly moves to the right.

### Moving with `top`

The `top` property can also be transitioned.

```css
.box {
    position: relative;
    top: 0;
    transition: top 0.5s ease;
}

.box:hover {
    top: -20px;
}
```

The element smoothly moves upward.

### Transform vs Position Properties

There is an important difference between using `transform` and properties such as `left` or `top`.

Using `transform`:

```css
.box {
    transform: translateX(0);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

Using `left`:

```css
.box {
    position: relative;
    left: 0;
    transition: left 0.3s ease;
}

.box:hover {
    left: 50px;
}
```

Both can create movement, but `transform` is commonly preferred for visual movement because it does not change the element's layout position in the same way as layout properties.

### Card Hover Effect

A common example is moving a card slightly upward.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

This creates a subtle lifting effect.

### Combining Position with Other Properties

Position transitions can be combined with colors, shadows, and other effects.

```css
.card {
    background-color: white;
    transform: translateY(0);
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);

    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    background-color: lightgray;
    transform: translateY(-8px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

The card smoothly moves upward while its background and shadow change.

### Practical Example

```html
<div class="box">
    <h2>Move Me</h2>
</div>
```

```css
.box {
    width: 200px;
    padding: 20px;
    background-color: steelblue;
    color: white;

    transform: translateX(0);
    transition: transform 0.5s ease;
}

.box:hover {
    transform: translateX(40px);
}
```

When the user hovers over the box, it smoothly moves `40px` to the right.

> 💡 **Tip:** For simple visual movement, prefer `transform: translate()` with a transition. Use layout properties such as `top` or `left` when you specifically need to change an element's positioned layout.

> 💡 **Remember:** A transition can make position changes smooth, but `transform` is commonly used for efficient visual movement effects.

---

## Practical Examples

CSS transitions are most useful when they are applied to real interface elements. The following examples combine the transition concepts covered in this chapter.

### 1. Button Hover Effect

A button can smoothly change its background color and size when the user hovers over it.

```html
<button class="button">Hover Me</button>
```

```css
.button {
    padding: 12px 24px;
    background-color: steelblue;
    color: white;
    border: none;
    cursor: pointer;

    transition:
        background-color 0.3s ease,
        transform 0.3s ease;
}

.button:hover {
    background-color: darkblue;
    transform: scale(1.05);
}
```

The button smoothly changes its background color and becomes slightly larger.

### 2. Card Lift Effect

A card can move upward and change its shadow when hovered.

```html
<div class="card">
    <h2>CSS Card</h2>
    <p>Hover over this card.</p>
</div>
```

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;

    transform: translateY(0);
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

The card smoothly moves upward and gains a larger shadow.

### 3. Navigation Link Effect

Navigation links can smoothly change their text color.

```html
<a href="#" class="nav-link">Home</a>
```

```css
.nav-link {
    color: black;
    text-decoration: none;

    transition: color 0.3s ease;
}

.nav-link:hover {
    color: steelblue;
}
```

The text color gradually changes when the pointer moves over the link.

### 4. Image Zoom Effect

A transition can be combined with `transform: scale()` to create a smooth image zoom.

```html
<div class="image-container">
    <img src="image.jpg" alt="Example" class="image">
</div>
```

```css
.image-container {
    overflow: hidden;
}

.image {
    display: block;
    transition: transform 0.4s ease;
}

.image:hover {
    transform: scale(1.05);
}
```

The image smoothly grows when hovered.

### 5. Input Focus Effect

Transitions can provide visual feedback when an input receives focus.

```html
<input type="text" class="input" placeholder="Enter your name">
```

```css
.input {
    padding: 10px;
    border: 2px solid gray;
    outline: none;

    transition: border-color 0.3s ease;
}

.input:focus {
    border-color: steelblue;
}
```

The border color changes smoothly when the user focuses on the input.

### 6. Expanding Button

A button can smoothly increase its width when hovered.

```css
.button {
    width: 120px;
    padding: 12px;

    transition: width 0.3s ease;
}

.button:hover {
    width: 180px;
}
```

The button expands from `120px` to `180px`.

### 7. Moving Element

An element can smoothly move horizontally using `translateX()`.

```css
.box {
    transform: translateX(0);
    transition: transform 0.5s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

The element moves `50px` to the right when hovered.

### 8. Rotating Icon

A transition can create a smooth rotation effect.

```css
.icon {
    transform: rotate(0deg);
    transition: transform 0.3s ease;
}

.icon:hover {
    transform: rotate(45deg);
}
```

The icon smoothly rotates by `45deg`.

### 9. Fade Effect

The `opacity` property can be transitioned to create a fade effect.

```css
.image {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.image:hover {
    opacity: 0.6;
}
```

The element gradually becomes more transparent.

### 10. Combined Card Effect

Several transition effects can be combined into one component.

```html
<div class="product-card">
    <h2>Product</h2>
    <p>Example product card.</p>
    <button>View Product</button>
</div>
```

```css
.product-card {
    width: 280px;
    padding: 20px;
    background-color: white;
    transform: translateY(0);

    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}

.product-card:hover {
    transform: translateY(-8px);
    background-color: lightgray;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.product-card button {
    background-color: steelblue;
    color: white;
    border: none;
    padding: 10px 18px;

    transition:
        background-color 0.3s ease,
        transform 0.3s ease;
}

.product-card button:hover {
    background-color: darkblue;
    transform: scale(1.05);
}
```

This example combines:

- `transform`
- `background-color`
- `box-shadow`
- `transition-duration`
- `transition-timing-function`
- `:hover`
- Multiple transitions

### Choosing a Suitable Transition

The transition should match the type of interaction.

```text
Color change
    ↓
0.2s – 0.4s

Small movement
    ↓
0.2s – 0.4s

Card movement
    ↓
0.3s – 0.5s

Image zoom
    ↓
0.3s – 0.5s

Large visual change
    ↓
Use a duration that does not feel unnecessarily slow
```

These are practical starting points rather than strict rules. The appropriate duration depends on the interface and the amount of visual change.

### Practical Example Combining the Main Concepts

```html
<div class="card">
    <h2>Learn CSS</h2>
    <p>Explore CSS transitions.</p>
    <button class="button">Learn More</button>
</div>
```

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;

    transform: translateY(0);
    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    background-color: lightgray;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.button {
    background-color: steelblue;
    color: white;
    border: none;
    padding: 10px 18px;

    transition:
        background-color 0.3s ease,
        transform 0.3s ease;
}

.button:hover {
    background-color: darkblue;
    transform: scale(1.05);
}
```

This demonstrates how multiple simple transitions can work together to create a polished interactive component.

> 💡 **Tip:** Start with small, subtle transitions and adjust the duration and timing function based on how the interaction feels.

> 💡 **Remember:** Good transition effects should make interactions clearer and smoother without distracting the user.

---

## Key Takeaways

CSS transitions allow CSS properties to change smoothly from one value to another instead of changing immediately.

### 1. `transition` Controls Smooth Changes

The `transition` property defines how a CSS property should change over time.

```css
.button {
    transition: background-color 0.3s ease;
}
```

### 2. `transition-property`

Specifies which CSS property should transition.

```css
.box {
    transition-property: transform;
}
```

### 3. `transition-duration`

Specifies how long the transition takes.

```css
.box {
    transition-duration: 0.5s;
}
```

### 4. `transition-timing-function`

Controls the speed pattern of the transition.

Common values include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

Example:

```css
.box {
    transition-timing-function: ease-out;
}
```

### 5. `transition-delay`

Specifies how long the browser waits before starting the transition.

```css
.box {
    transition-delay: 0.2s;
}
```

### 6. Transition Shorthand

The individual transition properties can be combined using the `transition` shorthand.

```css
.box {
    transition: transform 0.3s ease 0.1s;
}
```

The general form is:

```css
transition: property duration timing-function delay;
```

### 7. Multiple Transitions

Multiple properties can be transitioned by separating the transitions with commas.

```css
.box {
    transition:
        transform 0.3s ease,
        background-color 0.3s ease;
}
```

### 8. Transitions and `:hover`

Transitions are commonly used with the `:hover` pseudo-class.

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The transition should generally be placed on the normal state.

### 9. Transitions with `transform`

Transitions can create smooth movement, scaling, and rotation effects.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

### 10. Transitions with Colors

Color-related properties can be transitioned smoothly.

```css
.link {
    color: black;
    transition: color 0.3s ease;
}

.link:hover {
    color: steelblue;
}
```

Common color properties include:

- `color`
- `background-color`
- `border-color`

### 11. Transitions with Size

Properties such as `width` and `height` can be transitioned.

```css
.box {
    width: 150px;
    transition: width 0.5s ease;
}

.box:hover {
    width: 250px;
}
```

For visual scaling effects, `transform: scale()` is often a useful alternative.

### 12. Transitions with Position

Position-related effects can be created using `transform` or positioned properties.

```css
.box {
    transform: translateX(0);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

### 13. Transitions Do Not Create New States

A transition controls how a property changes. It does not define the new value itself.

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
:hover
    ↓
Defines the changed state

transform
    ↓
Defines the new value

transition
    ↓
Controls how the change happens
```

### 14. Transitions vs Animations

Transitions are generally used for changes between states, such as:

```text
Normal → Hover
Normal → Focus
Normal → Active
```

CSS animations are better suited to more complex sequences that can run through multiple stages.

### 15. Keep Transitions Subtle

Good transitions should improve the interface without distracting the user.

For example:

```css
.button {
    transition: background-color 0.3s ease;
}
```

A short, subtle transition is often more appropriate than an unnecessarily long effect.

### Quick Reference

| Property | Purpose |
| --- | --- |
| `transition-property` | Specifies what property changes |
| `transition-duration` | Specifies how long the change takes |
| `transition-timing-function` | Controls the speed pattern |
| `transition-delay` | Specifies when the transition starts |
| `transition` | Shorthand for transition properties |

### Complete Example

```css
.card {
    background-color: white;
    transform: translateY(0);
    transition:
        background-color 0.3s ease,
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    background-color: lightgray;
    transform: translateY(-8px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

This example combines several concepts from the chapter into one practical interaction.

> 💡 **Remember:** CSS transitions make property changes smooth. The four main transition components are **property, duration, timing function, and delay**.

> 💡 **Key idea:** Define the state change separately and use `transition` to control how smoothly the browser moves between the states.

---

## References

The following references can be used to further study CSS transitions and the related CSS properties covered in this chapter.

### MDN Web Docs

- CSS Transitions
- `transition`
- `transition-property`
- `transition-duration`
- `transition-timing-function`
- `transition-delay`

### CSS Specifications

- CSS Transitions Module
- CSS Transforms Module

### Related CSS Topics

The following topics are closely related to CSS transitions:

- CSS Transform
- CSS Animation
- CSS Pseudo-classes
- CSS Timing Functions
- CSS Transforms
- CSS Visual Effects

> 💡 **Tip:** Use the references to verify syntax, browser behavior, supported values, and advanced transition features.

> 💡 **Remember:** The examples in this chapter are intended to build a practical understanding of CSS transitions. For complete and up-to-date specifications, refer to the official CSS documentation.

---

## Quick Revision

This section provides a quick revision of the main concepts covered in the CSS Transitions chapter.

### What Is a CSS Transition?

A CSS transition allows a CSS property to change smoothly from one value to another over a specified period of time.

```css
.box {
    transition: background-color 0.3s ease;
}
```

### Main Transition Properties

CSS provides four main transition properties:

```text
transition-property
transition-duration
transition-timing-function
transition-delay
```

They control different parts of a transition.

| Property | Purpose |
| --- | --- |
| `transition-property` | Specifies which property should transition |
| `transition-duration` | Specifies how long the transition takes |
| `transition-timing-function` | Controls the speed pattern |
| `transition-delay` | Specifies when the transition starts |

### Transition Shorthand

The four properties can be combined using the `transition` shorthand.

```css
.box {
    transition: transform 0.3s ease 0.1s;
}
```

General form:

```css
transition: property duration timing-function delay;
```

### Common Timing Functions

```text
ease
linear
ease-in
ease-out
ease-in-out
```

Example:

```css
.box {
    transition: transform 0.3s ease-out;
}
```

### Multiple Transitions

Multiple properties can be transitioned by separating them with commas.

```css
.box {
    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        opacity 0.3s ease;
}
```

### Transitions with `:hover`

Transitions are commonly used with the `:hover` pseudo-class.

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The transition should generally be placed on the normal state.

### Transitions with `transform`

Transforms can be used to create smooth movement, scaling, and rotation effects.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

Common transform functions include:

```text
translate()
translateX()
translateY()
scale()
rotate()
```

### Transitions with Colors

Color properties can be transitioned smoothly.

```css
.button {
    background-color: steelblue;
    color: white;

    transition:
        background-color 0.3s ease,
        color 0.3s ease;
}
```

Common examples include:

```text
color
background-color
border-color
```

### Transitions with Size

Size-related properties can also be transitioned.

```css
.box {
    width: 150px;
    transition: width 0.5s ease;
}

.box:hover {
    width: 250px;
}
```

For visual scaling effects, `transform: scale()` is often another useful approach.

### Transitions with Position

Movement can be created using `transform` or positioned properties.

```css
.box {
    transform: translateX(0);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

### Transition vs Animation

Transitions are generally used when an element moves between states.

```text
Normal → Hover
Normal → Focus
Normal → Active
```

CSS animations are better suited to more complex sequences involving multiple stages.

### Important Relationship

Remember the roles of the different CSS features:

```text
:hover
   ↓
Defines the changed state

CSS property
   ↓
Defines what changes

transition
   ↓
Defines how smoothly it changes
```

For example:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

### Quick Syntax Reference

```css
/* Property */
transition-property: transform;

/* Duration */
transition-duration: 0.3s;

/* Timing function */
transition-timing-function: ease;

/* Delay */
transition-delay: 0.1s;

/* Shorthand */
transition: transform 0.3s ease 0.1s;
```

### Complete Example

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;
    transform: translateY(0);

    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    background-color: lightgray;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

This example combines:

- `transition-property`
- `transition-duration`
- `transition-timing-function`
- Multiple transitions
- `:hover`
- `transform`
- `background-color`
- `box-shadow`

### Final Revision Points

```text
CSS Transition
    ↓
Smoothly changes a property between states

transition-property
    ↓
What changes?

transition-duration
    ↓
How long does it take?

transition-timing-function
    ↓
How does the speed change?

transition-delay
    ↓
When does it start?

transition
    ↓
Shorthand for the transition properties
```

> 💡 **Remember:** The most important idea is that a transition controls the change between two states. It does not create the state itself.

> 💡 **Quick Formula:** `transition = property + duration + timing function + delay`

---

## Best Practices

Following good practices when using CSS transitions helps create interfaces that are smooth, consistent, accessible, and easy to maintain.

### 1. Keep Transitions Subtle

Transitions should improve the user experience without becoming distracting.

A short transition is often enough for small interface interactions:

```css
.button {
    transition: background-color 0.3s ease;
}
```

Avoid unnecessarily long transitions for simple interactions:

```css
.button {
    transition: background-color 3s ease;
}
```

The appropriate duration depends on the type of interaction and the amount of visual change.

### 2. Put the Transition on the Base State

Define the transition on the normal state rather than only on the `:hover` state.

Recommended:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

Avoid:

```css
.button:hover {
    transition: background-color 0.3s ease;
    background-color: darkblue;
}
```

Putting the transition on the base element allows the transition to work when entering and leaving the hover state.

### 3. Transition Only the Properties You Need

When possible, specify the properties that should transition.

```css
.card {
    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}
```

This is often clearer than:

```css
.card {
    transition: all 0.3s ease;
}
```

Using explicit properties makes the intended behavior easier to understand and maintain.

### 4. Use `transform` for Visual Movement

For simple visual movement, `transform` is commonly preferred.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

This is commonly useful for:

- Moving elements
- Scaling elements
- Rotating elements
- Creating hover effects

### 5. Choose an Appropriate Timing Function

Different timing functions create different visual effects.

```css
.button {
    transition: transform 0.3s ease;
}
```

Common choices include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

For many ordinary interface interactions, `ease` or `ease-out` can be a good starting point.

### 6. Use Consistent Durations

Using similar durations for similar interactions can make an interface feel more consistent.

For example:

```css
.button {
    transition: background-color 0.3s ease;
}

.link {
    transition: color 0.3s ease;
}

.card {
    transition: transform 0.3s ease;
}
```

This creates a consistent interaction pattern across the interface.

### 7. Avoid Excessive Transitions

Not every property needs a transition.

For example, adding transitions to too many properties can make an interface feel unnecessarily animated:

```css
.element {
    transition: all 0.5s ease;
}
```

Instead, identify the properties that actually need a visual transition.

```css
.element {
    transition:
        transform 0.3s ease,
        opacity 0.3s ease;
}
```

### 8. Use Transitions for User Feedback

Transitions are particularly useful when they communicate a change of state.

Examples include:

```text
Hover
Focus
Active
Selected
Expanded
```

For example:

```css
.input {
    border-color: gray;
    transition: border-color 0.2s ease;
}

.input:focus {
    border-color: steelblue;
}
```

The transition provides visual feedback when the input receives focus.

### 9. Consider Accessibility

Some users may prefer reduced motion.

CSS provides the `prefers-reduced-motion` media feature to allow reduced-motion preferences to be respected.

For example:

```css
.button {
    transition: transform 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
}

@media (prefers-reduced-motion: reduce) {
    .button {
        transition: none;
    }
}
```

This allows the transition to be disabled for users who have requested reduced motion.

### 10. Avoid Unnecessary Movement

Transitions should not make important content difficult to follow.

Avoid excessive:

- Movement
- Rotation
- Scaling
- Long delays
- Large visual changes

Use motion to support the interface rather than distract from its content.

### 11. Use Delays Carefully

A delay can be useful in specific situations:

```css
.menu {
    transition: opacity 0.3s ease 0.1s;
}
```

However, unnecessary delays can make an interface feel slow.

Use delays when they have a clear purpose.

### 12. Keep CSS Maintainable

Use clear transition declarations:

```css
.card {
    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}
```

This makes it easier to understand which properties are being transitioned.

### 13. Test Different States

When creating a transition, test the element in different states.

For example:

```text
Normal
   ↓
Hover
   ↓
Normal
```

Also consider:

```text
Normal
   ↓
Focus
   ↓
Normal
```

The transition should feel natural in both directions.

### 14. Do Not Use Transitions Everywhere

Transitions are useful, but they are not required for every CSS property or component.

Use them when they provide meaningful visual feedback or improve the interaction.

### Practical Example

```css
.card {
    width: 250px;
    padding: 20px;
    background-color: white;
    transform: translateY(0);

    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    background-color: lightgray;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

@media (prefers-reduced-motion: reduce) {
    .card {
        transition: none;
    }
}
```

This example follows several good practices:

- Uses specific transition properties.
- Uses a short duration.
- Uses `transform` for movement.
- Keeps the transition on the base state.
- Provides a reduced-motion alternative.

> 💡 **Tip:** Good transitions should feel natural enough that users notice the interaction, but not so much that the animation becomes the focus.

> 💡 **Remember:** Use transitions intentionally, keep them consistent, prefer efficient visual transforms for movement, and consider reduced-motion preferences.

---

## Common Mistakes

Understanding common mistakes helps avoid unexpected transition behavior and makes CSS easier to maintain.

### 1. Putting `transition` Only on `:hover`

A common mistake is defining the transition only inside the hover state.

Incorrect:

```css
.button:hover {
    transition: background-color 0.3s ease;
    background-color: darkblue;
}
```

Better:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

The transition should generally be placed on the normal state.

### 2. Using `transition: all` Unnecessarily

Using `all` transitions every property that can transition.

```css
.card {
    transition: all 0.3s ease;
}
```

Although this can work, it is often better to specify the required properties.

```css
.card {
    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}
```

This makes the intended behavior clearer.

### 3. Forgetting the Duration

A transition needs a duration greater than zero to produce a visible time-based effect.

For example:

```css
.box {
    transition-property: transform;
}
```

This does not specify how long the transition should take.

Instead:

```css
.box {
    transition: transform 0.3s ease;
}
```

### 4. Using an Incorrect Property Name

The property in the transition must correspond to the property that actually changes.

Incorrect:

```css
.box {
    transition: color 0.3s ease;
}

.box:hover {
    background-color: blue;
}
```

Here, `color` is not changing.

Correct:

```css
.box {
    transition: background-color 0.3s ease;
}

.box:hover {
    background-color: blue;
}
```

### 5. Expecting Every CSS Property to Transition

Not every CSS property behaves the same way during transitions.

For example, properties that represent discrete states may not produce a gradual visual change.

A common example is:

```css
.box {
    transition: display 0.3s ease;
}
```

Changing `display` does not work like smoothly transitioning a numeric or color value.

For effects such as fading an element, `opacity` is often more appropriate:

```css
.box {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.box:hover {
    opacity: 0;
}
```

### 6. Using `width` or `height` When `transform` Is More Appropriate

For a simple visual zoom effect, changing dimensions may be unnecessary.

Instead of:

```css
.card {
    width: 250px;
    transition: width 0.3s ease;
}

.card:hover {
    width: 260px;
}
```

A visual scaling effect can use:

```css
.card {
    transform: scale(1);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: scale(1.04);
}
```

The two approaches have different layout behavior, so choose based on the intended effect.

### 7. Using Very Long Durations

A transition that is too slow can make an interface feel unresponsive.

For example:

```css
.button {
    transition: background-color 5s ease;
}
```

A shorter duration is usually more appropriate for a simple interaction:

```css
.button {
    transition: background-color 0.3s ease;
}
```

The ideal duration depends on the design and interaction.

### 8. Using Excessive Delays

A delay can make an interaction feel slow if it is not necessary.

```css
.button {
    transition: transform 0.3s ease 2s;
}
```

For most simple hover interactions, an unnecessary delay should be avoided.

### 9. Forgetting Other Interaction States

A transition may be designed only for `:hover` while keyboard users interact with the element through focus.

For example:

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

For interactive controls, also consider an appropriate `:focus-visible` state:

```css
.button:focus-visible {
    outline: 2px solid currentColor;
    outline-offset: 2px;
}
```

Transitions should support interaction without removing useful focus indicators.

### 10. Ignoring Reduced Motion

Some users prefer less motion.

A transition can be disabled when the user has enabled a reduced-motion preference.

```css
.button {
    transition: transform 0.3s ease;
}

.button:hover {
    transform: scale(1.05);
}

@media (prefers-reduced-motion: reduce) {
    .button {
        transition: none;
    }
}
```

### 11. Making Transitions Too Dramatic

Large rotations, extreme scaling, or excessive movement can distract users.

Avoid unnecessary effects such as:

```css
.card:hover {
    transform: rotate(20deg) scale(1.5);
}
```

A smaller effect is often more appropriate:

```css
.card:hover {
    transform: translateY(-8px) scale(1.03);
}
```

### 12. Forgetting That Transitions Need a State Change

A transition does not automatically create an animation.

This alone does not produce a visible effect:

```css
.box {
    transition: transform 0.3s ease;
}
```

There must be a different value in another state:

```css
.box:hover {
    transform: translateX(30px);
}
```

The transition then controls the change between the two values.

### 13. Overusing Transitions

Adding transitions to every interactive element can make a page feel unnecessarily animated.

Use transitions where they provide useful feedback or improve the experience.

### Quick Mistake Checklist

```text
❌ Transition only inside :hover
❌ Use transition: all without a reason
❌ Forget the duration
❌ Transition the wrong property
❌ Expect every property to transition smoothly
❌ Use unnecessarily long durations
❌ Add unnecessary delays
❌ Ignore keyboard focus
❌ Ignore reduced-motion preferences
❌ Use excessive movement or scaling
❌ Forget to create an actual state change
❌ Add transitions everywhere
```

> 💡 **Tip:** When a transition does not work, first check three things: **the property being changed, the transition declaration, and whether the element actually changes state.**

> 💡 **Remember:** A transition only controls the change between values. It does not create the changed state by itself.

---

## Interview Questions

### 1. What are CSS transitions?

CSS transitions allow a CSS property to change smoothly from one value to another over a specified period of time.

```css
.button {
    transition: background-color 0.3s ease;
}
```

### 2. What is the purpose of the `transition` property?

The `transition` property controls how smoothly a CSS property changes between two states.

For example:

```css
.box {
    transition: transform 0.3s ease;
}
```

### 3. What are the four main transition properties?

The four main transition properties are:

```text
transition-property
transition-duration
transition-timing-function
transition-delay
```

### 4. What does `transition-property` do?

`transition-property` specifies which CSS property should transition.

```css
.box {
    transition-property: transform;
}
```

### 5. What does `transition-duration` do?

`transition-duration` specifies how long the transition takes to complete.

```css
.box {
    transition-duration: 0.5s;
}
```

### 6. What does `transition-timing-function` do?

It controls how the speed of the transition changes during its duration.

Common values include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

Example:

```css
.box {
    transition-timing-function: ease-out;
}
```

### 7. What does `transition-delay` do?

`transition-delay` specifies how long the browser waits before starting the transition.

```css
.box {
    transition-delay: 0.2s;
}
```

### 8. What is the shorthand syntax for transitions?

The `transition` shorthand can combine the main transition properties.

```css
.box {
    transition: transform 0.3s ease 0.1s;
}
```

General form:

```css
transition: property duration timing-function delay;
```

### 9. Can multiple properties be transitioned?

Yes. Multiple transitions can be separated using commas.

```css
.card {
    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}
```

### 10. How are transitions commonly used with `:hover`?

A transition can be defined on the normal state and the changed value can be defined in `:hover`.

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

### 11. Where should the `transition` property normally be placed?

It is generally placed on the base or normal state.

```css
.button {
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

This allows the transition to work when entering and leaving the hover state.

### 12. Can `transform` be used with transitions?

Yes. Transitions are commonly combined with `transform` for movement, scaling, and rotation.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

### 13. What is the difference between `transform` and `transition`?

`transform` defines the visual transformation.

`transition` controls how smoothly the transformation occurs.

```css
.card {
    transform: translateY(0);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
}
```

Here:

```text
transform
    ↓
Defines the movement

transition
    ↓
Controls the smoothness of the movement
```

### 14. Can colors be transitioned?

Yes. Common color properties such as `color`, `background-color`, and `border-color` can be transitioned.

```css
.button {
    background-color: steelblue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}
```

### 15. Can width and height be transitioned?

Yes.

```css
.box {
    width: 150px;
    transition: width 0.4s ease;
}

.box:hover {
    width: 250px;
}
```

For visual scaling, `transform: scale()` can also be used.

### 16. What is the difference between `width` transition and `transform: scale()`?

A `width` transition changes the element's width.

```css
.box {
    width: 150px;
    transition: width 0.3s ease;
}

.box:hover {
    width: 200px;
}
```

A scale transform visually enlarges the element.

```css
.box {
    transform: scale(1);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.1);
}
```

They can produce different layout behavior.

### 17. Can position changes be transitioned?

Yes. Position-related effects can be created using `transform` or positioned properties such as `top` and `left`.

Example using `transform`:

```css
.box {
    transform: translateX(0);
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(50px);
}
```

### 18. What is the difference between CSS transitions and animations?

Transitions are generally used for changes between states.

```text
Normal → Hover
Normal → Focus
Normal → Active
```

Animations are better suited to more complex sequences involving multiple stages.

### 19. Does a transition create an animation by itself?

No.

A transition controls how a property changes between values. There must be a state change or another change in the property's value.

For example:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.05);
}
```

The `:hover` state creates the changed value, while the transition controls the change.

### 20. What does `transition: all` mean?

It tells the browser to transition all properties that support transitions when their values change.

```css
.box {
    transition: all 0.3s ease;
}
```

However, explicitly listing the required properties can make the CSS clearer and more predictable.

### 21. Why can `transition: all` be discouraged?

Using `all` can cause properties to transition that were not intended to animate.

Instead:

```css
.card {
    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}
```

This clearly specifies the intended properties.

### 22. What happens if the transition duration is `0s`?

The property change happens without a visible time-based transition.

```css
.box {
    transition: transform 0s ease;
}
```

There is effectively no gradual transition.

### 23. Can transitions be combined with multiple CSS properties?

Yes.

```css
.card {
    transition:
        transform 0.3s ease,
        background-color 0.3s ease,
        box-shadow 0.3s ease;
}
```

Each property can have its own transition settings.

### 24. How can transitions support accessibility?

Users who prefer reduced motion can be supported using `prefers-reduced-motion`.

```css
.button {
    transition: transform 0.3s ease;
}

@media (prefers-reduced-motion: reduce) {
    .button {
        transition: none;
    }
}
```

### 25. What are some best practices for CSS transitions?

Important practices include:

- Keep transitions subtle.
- Use appropriate durations.
- Specify the properties that should transition.
- Prefer `transform` for simple visual movement.
- Avoid unnecessary delays.
- Consider keyboard focus.
- Support reduced-motion preferences.
- Avoid excessive animation.
- Keep transition behavior consistent.

### Quick Interview Revision

```text
CSS Transition
    ↓
Smoothly changes a property between states

transition-property
    ↓
What changes?

transition-duration
    ↓
How long does it take?

transition-timing-function
    ↓
How does the speed change?

transition-delay
    ↓
When does it start?

transition
    ↓
Shorthand for transition properties

transform
    ↓
Defines visual transformation

:hover / :focus
    ↓
Can define the changed state
```

> 💡 **Interview Tip:** If asked about CSS transitions, remember the four main components: **property, duration, timing function, and delay**.

> 💡 **Key distinction:** `transition` controls **how a change happens**, while the CSS state or rule defines **what changes**.

---

## Practice Exercises

The following exercises are designed to reinforce the concepts covered in the CSS Transitions chapter.

### Exercise 1: Basic Color Transition

Create a button that changes its background color smoothly when the user hovers over it.

Requirements:

- Use `background-color`.
- Add a transition.
- Use a duration of `0.3s`.
- Use `ease` as the timing function.

Expected behavior:

```text
Normal → Blue
Hover  → Dark Blue
```

### Exercise 2: Text Color Transition

Create a navigation link that changes its text color when hovered.

Requirements:

- Use the `color` property.
- Add a transition.
- Do not use `transition: all`.

### Exercise 3: Moving Card

Create a card that moves upward by `10px` when hovered.

Requirements:

- Use `transform: translateY()`.
- Add a transition to `transform`.
- Use a duration between `0.3s` and `0.5s`.

Expected behavior:

```text
Normal
   ↓
Card at original position

Hover
   ↓
Card moves upward
```

### Exercise 4: Scaling Button

Create a button that becomes slightly larger when hovered.

Requirements:

- Use `transform: scale()`.
- Add a transition.
- Use a subtle scale value such as `1.05`.

### Exercise 5: Rotating Icon

Create an element that rotates when hovered.

Requirements:

- Start at `rotate(0deg)`.
- Rotate to `rotate(45deg)`.
- Transition the `transform` property.

### Exercise 6: Expanding Box

Create a box that smoothly increases its width.

Requirements:

- Initial width: `150px`.
- Hover width: `250px`.
- Transition the `width` property.
- Use a duration of `0.5s`.

### Exercise 7: Multiple Transitions

Create a card that changes multiple properties when hovered.

Requirements:

- Change `background-color`.
- Move the card upward using `transform`.
- Change `box-shadow`.
- Use separate transition declarations for the properties.

Example structure:

```css
.card {
    transition:
        background-color 0.3s ease,
        transform 0.3s ease,
        box-shadow 0.3s ease;
}
```

### Exercise 8: Input Focus Transition

Create an input field whose border changes color smoothly when it receives focus.

Requirements:

- Use `:focus`.
- Transition `border-color`.
- Do not remove the focus indicator.

Expected behavior:

```text
Normal → Gray border
Focus  → Blue border
```

### Exercise 9: Image Zoom

Create an image that slightly zooms when the user hovers over it.

Requirements:

- Use `transform: scale()`.
- Use `overflow: hidden` on a suitable container if needed.
- Add a smooth transition.

Try:

```css
transform: scale(1.05);
```

### Exercise 10: Transition Delay

Create a button that waits briefly before its hover transition begins.

Requirements:

- Use `transition-delay`.
- Use a delay of approximately `0.2s`.
- Transition the background color.

### Exercise 11: Timing Functions

Create four boxes and give each one a different timing function.

Use:

```text
ease
linear
ease-in
ease-out
```

Compare how the movement feels for each box.

### Exercise 12: Transition Shorthand

Rewrite the following individual properties using the `transition` shorthand:

```css
.box {
    transition-property: transform;
    transition-duration: 0.4s;
    transition-timing-function: ease;
    transition-delay: 0.1s;
}
```

Your result should use one `transition` declaration.

### Exercise 13: Fix the Mistake

The following code does not provide the intended transition behavior:

```css
.button:hover {
    transition: background-color 0.3s ease;
    background-color: darkblue;
}
```

Rewrite it so that the transition works when entering and leaving the hover state.

### Exercise 14: Avoid `transition: all`

Rewrite this code:

```css
.card {
    transition: all 0.3s ease;
}
```

Assume that only these properties should transition:

```text
transform
box-shadow
```

Write a more specific transition declaration.

### Exercise 15: Reduced Motion

Create a button with a scale transition and add a `prefers-reduced-motion` media query.

Requirements:

- Normal state uses a transition.
- Hover state uses `transform: scale()`.
- Reduced-motion users should not receive the transition.

### Exercise 16: Complete Interactive Card

Create a complete card component containing:

```text
Title
Description
Button
```

When the user hovers over the card:

- Move the card upward.
- Change its background color.
- Increase its shadow.

When the user hovers over the button:

- Change its background color.
- Slightly scale the button.

Use multiple transitions.

### Exercise 17: Debug the Transition

Find and fix the problem in this code:

```css
.box {
    background-color: steelblue;
    transition: color 0.3s ease;
}

.box:hover {
    background-color: darkblue;
}
```

Question:

**Which property should be transitioned?**

### Exercise 18: Compare `width` and `scale`

Create two boxes.

The first should become larger using:

```css
width
```

The second should become larger using:

```css
transform: scale()
```

Compare the visual and layout behavior of both approaches.

### Exercise 19: Build a Navigation Menu

Create a navigation menu with several links.

Each link should:

- Change color on hover.
- Transition smoothly.
- Have a visible keyboard focus state.

Example:

```text
Home
About
Services
Contact
```

### Exercise 20: Mini Project

Build a small interactive product card using the concepts from this chapter.

The card should include:

```text
Product image
Product name
Description
Price
Button
```

Add suitable transitions for:

- Card movement.
- Card shadow.
- Image scaling.
- Button color.
- Button scaling.

Also include support for:

```css
@media (prefers-reduced-motion: reduce)
```

### Practice Checklist

```text
⬜ Basic color transition
⬜ Text color transition
⬜ Card movement
⬜ Scale effect
⬜ Rotation effect
⬜ Width transition
⬜ Multiple transitions
⬜ Focus transition
⬜ Image zoom
⬜ Transition delay
⬜ Timing functions
⬜ Transition shorthand
⬜ Debug a transition
⬜ Avoid transition: all
⬜ Reduced-motion support
⬜ Complete interactive card
⬜ Navigation menu
⬜ Mini project
```

> 💡 **Tip:** Try to solve the exercises without immediately looking at existing examples. Writing the CSS yourself will help reinforce how `transition`, pseudo-classes, and changed property values work together.

> 💡 **Remember:** The goal is not just to memorize the syntax. Practice identifying **what changes**, **which property changes**, and **how that change should happen**.