# CSS Colors

## Table of Contents

- [Introduction](#introduction)
- [What are CSS Colors?](#what-are-css-colors)
- [Named Colors](#named-colors)
- [Hexadecimal Colors](#hexadecimal-colors)
- [RGB Colors](#rgb-colors)
- [RGBA Colors](#rgba-colors)
- [HSL Colors](#hsl-colors)
- [HSLA Colors](#hsla-colors)
- [Transparent Keyword](#transparent-keyword)
- [currentColor Keyword](#currentcolor-keyword)
- [Which Color Format Should You Use?](#which-color-format-should-you-use)
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

Colors play an essential role in web design. They help improve the appearance of a webpage, highlight important information, create visual hierarchy, and enhance the overall user experience.

CSS provides multiple ways to define colors, allowing developers to choose the format that best fits their needs. Some formats are simple and easy to read, while others offer greater flexibility, such as controlling transparency or adjusting hue, saturation, and lightness.

In this chapter, you'll learn the different ways to specify colors in CSS, understand when to use each format, and discover best practices for writing clean and maintainable styles.

> 💡 **Pro Tip:** Choosing the right color format isn't just about preference—it can make your CSS easier to read, maintain, and collaborate on, especially in larger projects.


---


## What are CSS Colors?

**CSS colors** are used to define the color of different parts of a webpage, such as text, backgrounds, borders, shadows, and other visual elements.

Colors are an important part of web design because they improve readability, emphasize important content, create visual hierarchy, and enhance the overall user experience.

### Why Do We Use CSS Colors?

CSS colors help developers:

- Improve the appearance of a webpage.
- Make text easier to read.
- Highlight important information.
- Create consistent branding and themes.
- Improve accessibility and user experience.

### Common CSS Properties That Use Colors

Many CSS properties accept color values. Some of the most commonly used ones are:

```css
h1 {
    color: navy;
    background-color: lightblue;
    border: 2px solid blue;
}
```

| Property | Purpose |
|----------|---------|
| `color` | Changes the text color. |
| `background-color` | Changes the background color of an element. |
| `border-color` | Sets the color of borders. |
| `outline-color` | Sets the color of outlines. |
| `text-decoration-color` | Changes the color of text decorations. |
| `box-shadow` | Can use colors for shadow effects. |

### Color Formats in CSS

CSS supports multiple ways to represent colors.

In this chapter, you'll learn:

- Named Colors
- Hexadecimal Colors
- RGB Colors
- RGBA Colors
- HSL Colors
- HSLA Colors
- `transparent`
- `currentColor`

Each format has its own advantages and is suitable for different situations.

> 💡 **Pro Tip:** Most browsers support all modern CSS color formats, so choose the one that makes your code the easiest to read and maintain rather than relying on just one format everywhere.

### Real-World Usage

You'll use CSS colors in almost every web project, including:

- Buttons and navigation menus
- Headers and footers
- Forms and input fields
- Cards and dashboards
- Alerts, badges, and notifications
- Themes (Light Mode and Dark Mode)


---


## Named Colors

**Named Colors** are predefined color names recognized by CSS. Instead of writing numeric color values, you can use descriptive names such as `red`, `blue`, or `green`.

CSS currently supports **more than 140 standard color names**, making this the simplest way to specify colors.

### Syntax

```css
selector {
    color: color-name;
}
```

### Example

**HTML**

```html
<h1>Developer Notes</h1>

<p>Learning CSS Colors.</p>

<button>Get Started</button>
```

**CSS**

```css
h1 {
    color: navy;
}

p {
    color: dimgray;
}

button {
    background-color: royalblue;
    color: white;
}
```

### Common Named Colors

| Color | Preview |
|--------|---------|
| `black` | ⚫ |
| `white` | ⚪ |
| `red` | 🔴 |
| `green` | 🟢 |
| `blue` | 🔵 |
| `yellow` | 🟡 |
| `orange` | 🟠 |
| `purple` | 🟣 |
| `gray` | ◻️ |
| `pink` | 🌸 |

### Advantages

- Easy to read and remember.
- Quick to use for simple projects.
- No need to remember numeric color values.
- Supported by all modern browsers.

### Limitations

- Limited to predefined color names.
- Not suitable when an exact brand or design color is required.
- Offers less flexibility compared to formats like Hex, RGB, or HSL.

> 💡 **Pro Tip:** Named colors are great for learning CSS and building quick prototypes. For production websites, designers and developers usually prefer **Hex**, **RGB**, or **HSL** because they provide much greater precision.

### Real-World Usage

Named colors are commonly used for:

- Learning and practicing CSS.
- Small personal projects.
- Quick prototypes and demonstrations.
- Temporary styling during development.


---


## Hexadecimal Colors

**Hexadecimal Colors** (or **Hex Colors**) represent colors using a combination of numbers and letters.

A hexadecimal color value starts with a **hash (`#`)** followed by **six hexadecimal characters**.

```text
#RRGGBB
```

Where:

- **RR** → Red
- **GG** → Green
- **BB** → Blue

Each pair ranges from **`00`** (no intensity) to **`FF`** (maximum intensity).

### Syntax

```css
selector {
    color: #RRGGBB;
}
```

### Example

**HTML**

```html
<h1>Developer Notes</h1>

<p>Learning CSS Colors.</p>

<button>Start Learning</button>
```

**CSS**

```css
h1 {
    color: #1E3A8A;
}

p {
    color: #4B5563;
}

button {
    background-color: #2563EB;
    color: #FFFFFF;
}
```

### Common Hex Colors

| Color | Hex Value |
|--------|-----------|
| Black | `#000000` |
| White | `#FFFFFF` |
| Red | `#FF0000` |
| Green | `#008000` |
| Blue | `#0000FF` |
| Yellow | `#FFFF00` |
| Gray | `#808080` |

### Short Hex Notation

When each color pair contains identical digits, you can use the shorter **3-digit** notation.

| Full Hex | Short Hex |
|----------|-----------|
| `#FFFFFF` | `#FFF` |
| `#000000` | `#000` |
| `#FF0000` | `#F00` |
| `#00FF00` | `#0F0` |
| `#0000FF` | `#00F` |

Both forms represent the same color.

### Advantages

- Widely used in web development.
- Compact and easy to copy from design tools.
- Provides precise color values.
- Supported by all modern browsers.

### Limitations

- Not as intuitive as HSL for adjusting colors.
- Does not include transparency (use **RGBA** or **8-digit Hex** if transparency is needed).

> 💡 **Pro Tip:** Most design tools such as Figma, Adobe XD, and Photoshop provide colors in Hex format, making it a common choice when converting designs into code.

### Real-World Usage

Hex colors are commonly used for:

- Website themes
- Brand colors
- Buttons and navigation bars
- Backgrounds
- Design systems


---


## RGB Colors

**RGB** stands for **Red, Green, and Blue**. It represents colors by combining different intensities of these three primary colors.

Each color component accepts a value from **0** to **255**:

- **0** → No intensity
- **255** → Maximum intensity

The browser mixes these values to produce the final color.

### Syntax

```css
selector {
    color: rgb(red, green, blue);
}
```

### Example

**HTML**

```html
<h1>Developer Notes</h1>

<p>Learning CSS Colors.</p>

<button>Start Learning</button>
```

**CSS**

```css
h1 {
    color: rgb(30, 58, 138);
}

p {
    color: rgb(75, 85, 99);
}

button {
    background-color: rgb(37, 99, 235);
    color: rgb(255, 255, 255);
}
```

### Understanding RGB Values

| Color | RGB Value |
|--------|-----------|
| Black | `rgb(0, 0, 0)` |
| White | `rgb(255, 255, 255)` |
| Red | `rgb(255, 0, 0)` |
| Green | `rgb(0, 128, 0)` |
| Blue | `rgb(0, 0, 255)` |
| Yellow | `rgb(255, 255, 0)` |

### Advantages

- Easy to understand once you know the RGB color model.
- Provides precise control over color values.
- Widely used in CSS and JavaScript.
- Supported by all modern browsers.

### Limitations

- The numeric values are less intuitive than named colors.
- Transparency is not supported directly (use **RGBA** instead).

> 💡 **Pro Tip:** If you're changing colors dynamically with JavaScript, you'll often work with RGB values because many browser APIs return colors in this format.

### 🌍 Real-World Usage

RGB colors are commonly used for:

- Dynamic color changes with JavaScript.
- Interactive UI components.
- Charts and data visualizations.
- Applications where colors are generated programmatically.

### 📌 Did You Know?

Modern CSS also supports **space-separated RGB syntax**, making it easier to combine with alpha values.

Example:

```css
color: rgb(30 58 138);
```

Both comma-separated and space-separated syntaxes are valid in modern browsers, but the comma-separated format is still the most commonly seen in existing codebases.


---


## RGBA Colors

**RGBA** stands for **Red, Green, Blue, and Alpha**. It extends the RGB color model by adding an **Alpha** channel, which controls the transparency (opacity) of a color.

The RGB values range from **0** to **255**, while the Alpha value ranges from:

- **0** → Completely transparent
- **1** → Completely opaque

Values between `0` and `1` create different transparency levels.

### Syntax

```css
selector {
    color: rgba(red, green, blue, alpha);
}
```

### Example

**HTML**

```html
<div class="card">
    Welcome to Developer Notes
</div>
```

**CSS**

```css
.card {
    background-color: rgba(37, 99, 235, 0.2);
    border: 2px solid rgb(37, 99, 235);
    padding: 20px;
}
```

In this example:

- The border is fully visible.
- The background uses the same blue color with **20% opacity**, allowing the content behind it to remain partially visible.

### Understanding the Alpha Value

| Alpha Value | Result |
|-------------|--------|
| `0` | Completely transparent |
| `0.25` | 25% opaque |
| `0.5` | 50% opaque |
| `0.75` | 75% opaque |
| `1` | Completely opaque |

### Advantages

- Supports transparency without affecting the entire element.
- Creates modern UI effects such as overlays and glass-like backgrounds.
- Useful for layering colors while keeping content visible.
- Fully supported by modern browsers.

### Limitations

- Slightly longer to write than RGB.
- If transparency is not needed, RGB or Hex may be simpler choices.

> 💡 **Pro Tip:** Prefer using **RGBA** when only the background should be transparent. Using the `opacity` property affects the entire element, including its text, images, and child elements.

### 🌍 Real-World Usage

RGBA is commonly used for:

- Modal overlays
- Transparent navigation bars
- Cards with semi-transparent backgrounds
- Hover effects
- Shadows and visual effects

### 📌 Did You Know?

The modern CSS Color specification also allows **space-separated RGB with alpha**.

Example:

```css
background-color: rgb(37 99 235 / 20%);
```

This is equivalent to:

```css
background-color: rgba(37, 99, 235, 0.2);
```

Both syntaxes are valid in modern browsers, although the traditional `rgba()` syntax is still widely used and easy for beginners to understand.

### ⚠️ Important

Do **not** confuse `opacity` with `rgba()`.

```css
/* Only the background is transparent */
background-color: rgba(0, 0, 0, 0.5);
```

```css
/* The entire element, including text and images, becomes transparent */
opacity: 0.5;
```

This distinction is important because it affects how the entire element is rendered.


---


## HSL Colors

**HSL** stands for **Hue, Saturation, and Lightness**. Instead of mixing Red, Green, and Blue values, HSL describes a color based on its position on the color wheel, its intensity, and its brightness.

Many developers find HSL easier to understand because it matches how humans naturally think about colors.

### Understanding HSL

An HSL color consists of three values:

```text
hsl(hue, saturation, lightness)
```

- **Hue (H)** → The color itself, measured in degrees (`0°`–`360°`).
- **Saturation (S)** → The intensity or richness of the color, measured as a percentage (`0%`–`100%`).
- **Lightness (L)** → How light or dark the color is, measured as a percentage (`0%`–`100%`).

### Hue (Color Wheel)

| Hue | Color |
|-----|-------|
| `0°` | 🔴 Red |
| `60°` | 🟡 Yellow |
| `120°` | 🟢 Green |
| `180°` | 🟦 Cyan |
| `240°` | 🔵 Blue |
| `300°` | 🟣 Purple |
| `360°` | 🔴 Red |

### Saturation

Saturation controls how vivid or dull a color appears.

| Value | Result |
|--------|--------|
| `0%` | Gray (no color) |
| `50%` | Moderately saturated |
| `100%` | Fully saturated |

### Lightness

Lightness controls how bright or dark a color appears.

| Value | Result |
|--------|--------|
| `0%` | Black |
| `50%` | Original color |
| `100%` | White |

### Syntax

```css
selector {
    color: hsl(hue, saturation, lightness);
}
```

### Example

**CSS**

```css
h1 {
    color: hsl(220, 65%, 45%);
}

button {
    background-color: hsl(210, 80%, 50%);
    color: white;
}
```

### Advantages

- Easier to adjust colors than RGB or Hex.
- Makes creating lighter or darker shades simple.
- Ideal for themes and design systems.
- Improves readability when working with color palettes.

### Limitations

- Less familiar to beginners than Hex or RGB.
- Not commonly provided directly by design tools.

> 💡 **Pro Tip:** If you need multiple shades of the same color, change only the **Lightness** value instead of searching for new Hex or RGB values. This keeps your color palette consistent.

### 🌍 Real-World Usage

HSL is commonly used for:

- Design systems
- Dark mode and light mode themes
- Creating consistent color palettes
- UI components with multiple shades of the same color

### 📌 Did You Know?

Many CSS frameworks and modern design systems internally use HSL because adjusting **Hue**, **Saturation**, or **Lightness** individually is much easier than recalculating RGB values.

### ⚠️ Important

Remember that **Hue**, **Saturation**, and **Lightness** work together.

Changing just one value can significantly change the appearance of the color while the other two remain the same.


---


## HSLA Colors

**HSLA** stands for **Hue, Saturation, Lightness, and Alpha**. It extends the HSL color model by adding an **Alpha** channel, which controls the transparency (opacity) of a color.

If you already understand HSL, HSLA is easy to learn—the only difference is the additional Alpha value.

### Understanding HSLA

An HSLA color consists of four values:

```text
hsla(hue, saturation, lightness, alpha)
```

Where:

- **Hue (H)** → The color, measured in degrees (`0°`–`360°`).
- **Saturation (S)** → The intensity of the color (`0%`–`100%`).
- **Lightness (L)** → The brightness of the color (`0%`–`100%`).
- **Alpha (A)** → The transparency of the color (`0`–`1`).

### Syntax

```css
selector {
    color: hsla(hue, saturation, lightness, alpha);
}
```

### Example

**CSS**

```css
.card {
    background-color: hsla(220, 80%, 50%, 0.2);
    border: 2px solid hsl(220, 80%, 50%);
    padding: 20px;
}
```

In this example:

- The border uses a fully opaque blue.
- The background uses the same blue with **20% opacity**.

### Understanding the Alpha Value

| Alpha Value | Result |
|-------------|--------|
| `0` | Completely transparent |
| `0.25` | 25% opaque |
| `0.5` | 50% opaque |
| `0.75` | 75% opaque |
| `1` | Completely opaque |

### HSL vs HSLA

| HSL | HSLA |
|-----|------|
| Uses Hue, Saturation, and Lightness | Adds an Alpha channel for transparency |
| No transparency support | Supports transparency |
| Best for defining colors | Best for defining transparent colors |

### Advantages

- Combines HSL's intuitive color model with transparency.
- Makes it easy to adjust both color and opacity.
- Great for overlays, cards, and modern UI components.
- Supported by all modern browsers.

### Limitations

- Slightly longer syntax than HSL.
- Transparency is unnecessary when a fully opaque color is sufficient.

> 💡 **Pro Tip:** If you're already using HSL in your project, prefer **HSLA** over switching to RGBA when transparency is needed. This keeps your color definitions consistent.

### 🌍 Real-World Usage

HSLA is commonly used for:

- Glassmorphism effects
- Modal backgrounds
- Transparent cards
- Hover effects
- Design systems with adjustable color themes

### 📌 Did You Know?

Modern CSS also supports **space-separated HSL with alpha**.

```css
background-color: hsl(220 80% 50% / 20%);
```

This is equivalent to:

```css
background-color: hsla(220, 80%, 50%, 0.2);
```

Both syntaxes are valid, but the traditional `hsla()` format is easier for beginners to recognize.

### ⚠️ Important

The **Alpha** value affects only the color itself.

If you use the `opacity` property instead, the **entire element**, including its text, images, and child elements, becomes transparent.


---


## Transparent Keyword

The **`transparent`** keyword represents a **fully transparent color**. It makes an element's color invisible while preserving the element itself.

Unlike `rgba()` or `hsla()`, you don't need to specify any color values—the browser automatically treats `transparent` as a completely transparent color.

### Syntax

```css
selector {
    property: transparent;
}
```

### Example

**HTML**

```html
<button>Learn CSS</button>
```

**CSS**

```css
button {
    background-color: transparent;
    border: 2px solid royalblue;
    color: royalblue;
}
```

In this example:

- The button has **no visible background color**.
- The border and text remain visible.

### Common Use Cases

- Transparent buttons
- Removing an element's background color
- Creating hover effects
- Transparent borders before animations
- Overlay and UI effects

### Advantages

- Very simple and readable.
- No need to remember alpha values.
- Supported by all modern browsers.
- Makes CSS easier to understand when complete transparency is needed.

### Limitations

- Always represents **100% transparency**.
- Cannot create partially transparent colors.
- Use **RGBA** or **HSLA** when different transparency levels are required.

> 💡 **Pro Tip:** Use `transparent` when you want **no visible color at all**. If you need **partial transparency**, choose `rgba()` or `hsla()` instead.

### 🌍 Real-World Usage

The `transparent` keyword is commonly used for:

- Ghost buttons
- Transparent navigation bars
- Hover effects
- Border animations
- Form elements with custom backgrounds

### 📌 Did You Know?

The `transparent` keyword is effectively equivalent to a fully transparent color.

For example:

```css
background-color: transparent;
```

Produces the same visual result as:

```css
background-color: rgba(0, 0, 0, 0);
```

Although they look the same, using `transparent` is often cleaner and easier to read.

### ⚠️ Important

The `transparent` keyword makes **only the color transparent**.

It does **not** hide the HTML element or remove it from the page. The element still occupies space and can still receive user interactions unless other CSS properties change its behavior.


---


## currentColor Keyword

The **`currentColor`** keyword represents the **current value of an element's `color` property**.

Instead of specifying the same color multiple times, you can use `currentColor` to automatically reuse the element's text color for other properties such as borders, outlines, shadows, and SVG graphics.

This makes your CSS cleaner, more consistent, and easier to maintain.

### Syntax

```css
selector {
    color: blue;
    border: 2px solid currentColor;
}
```

### Example

**HTML**

```html
<button class="btn">
    Get Started
</button>
```

**CSS**

```css
.btn {
    color: royalblue;
    border: 2px solid currentColor;
    background-color: transparent;
    padding: 10px 20px;
}
```

In this example:

- The button text is **royal blue**.
- The border automatically becomes **royal blue** because it uses `currentColor`.
- If the text color changes, the border color changes automatically.

### Another Example

```css
.card {
    color: darkgreen;
    box-shadow: 0 0 10px currentColor;
}
```

The shadow automatically uses the same color as the text.

### Advantages

- Reduces duplicate color values.
- Keeps components visually consistent.
- Makes CSS easier to maintain.
- Simplifies theme creation.
- Supported by all modern browsers.

### Limitations

- Depends on the value of the `color` property.
- May be confusing if you're unfamiliar with CSS inheritance.
- Not suitable when different properties require different colors.

> 💡 **Pro Tip:** `currentColor` is especially useful when building reusable UI components. Change the text color once, and related properties like borders or icons update automatically.

### 🌍 Real-World Usage

The `currentColor` keyword is commonly used for:

- Buttons
- Icons (especially SVG icons)
- Borders
- Outlines
- Box shadows
- Themeable UI components

### 📌 Did You Know?

Many modern UI libraries use `currentColor` for icons.

This allows an icon to automatically match the surrounding text color without writing additional CSS.

For example:

```css
.icon {
    fill: currentColor;
}
```

Changing the text color automatically updates the icon color as well.

### ⚠️ Important

`currentColor` always refers to the **computed value of the `color` property**.

If the `color` property changes because of inheritance, a class, or a pseudo-class such as `:hover`, every property using `currentColor` updates automatically.


---


## Which Color Format Should You Use?

CSS offers several ways to define colors, and each format has its own strengths. Choosing the right one depends on your project's requirements and the level of control you need.

| Color Format | Best Used For | Supports Transparency |
|--------------|---------------|:---------------------:|
| Named Colors | Learning, quick prototypes, simple examples | ❌ No |
| Hexadecimal | General web development, branding, design systems | ❌ No |
| RGB | JavaScript, dynamic color generation | ❌ No |
| RGBA | Overlays, shadows, transparent backgrounds | ✅ Yes |
| HSL | Creating and adjusting color palettes | ❌ No |
| HSLA | Themes, overlays, adjustable transparent colors | ✅ Yes |
| `transparent` | Completely transparent colors | ✅ Yes (fully transparent) |
| `currentColor` | Reusing an element's current text color | Depends on the `color` property |

### Recommended Usage

#### 🎨 Named Colors

Use when:

- Learning CSS.
- Creating quick prototypes.
- Writing simple examples.

Avoid using them when an exact color is required.

---

#### 🎨 Hexadecimal Colors

Use when:

- Working with design files.
- Implementing brand colors.
- Building production websites.

Hex is one of the most common color formats in frontend development.

---

#### 🎨 RGB Colors

Use when:

- Colors are generated or modified using JavaScript.
- Working with APIs that return RGB values.
- You need precise control over red, green, and blue values.

---

#### 🎨 RGBA Colors

Use when:

- Backgrounds need transparency.
- Creating overlays or glass-like effects.
- Building hover effects and shadows.

RGBA is preferred over the `opacity` property when only the color should be transparent.

---

#### 🎨 HSL Colors

Use when:

- Building design systems.
- Creating multiple shades of the same color.
- Developing light and dark themes.

HSL makes adjusting colors much easier than Hex or RGB.

---

#### 🎨 HSLA Colors

Use when:

- You need both HSL's flexibility and transparency.
- Creating modern UI components.
- Designing overlays and themed interfaces.

---

#### 🎨 `transparent`

Use when:

- No visible color is needed.
- Creating transparent buttons or backgrounds.
- Resetting background or border colors.

---

#### 🎨 `currentColor`

Use when:

- Building reusable components.
- Keeping borders, icons, and shadows consistent with text.
- Reducing repeated color values in your CSS.

---

> 💡 **Pro Tip:** There isn't a single "best" color format. Professional developers choose the format that makes their code the easiest to read, maintain, and update.

### 🌍 Real-World Recommendation

A typical modern project might use several color formats together:

- **Hex** for brand colors.
- **RGB/RGBA** when colors are generated dynamically or require transparency.
- **HSL/HSLA** when creating themes or adjusting color variations.
- **`transparent`** for transparent UI elements.
- **`currentColor`** for reusable, consistent components.

Using the right format for the right task results in cleaner, more maintainable CSS.


---


## Key Takeaways

- CSS provides multiple ways to define colors, each designed for different use cases.
- **Named Colors** are simple and useful for learning or quick prototypes.
- **Hexadecimal Colors** are widely used in production websites and design systems.
- **RGB** represents colors using Red, Green, and Blue values.
- **RGBA** extends RGB by adding transparency through an Alpha channel.
- **HSL** represents colors using Hue, Saturation, and Lightness, making color adjustments easier.
- **HSLA** extends HSL by adding transparency.
- The **`transparent`** keyword creates a fully transparent color.
- The **`currentColor`** keyword reuses the current value of an element's `color` property.
- Choosing the appropriate color format improves readability, maintainability, and scalability.

### Decision Guide

| If you need... | Recommended Format |
|----------------|--------------------|
| A simple color for learning or testing | Named Colors |
| Exact design or brand colors | Hexadecimal |
| Dynamic colors in JavaScript | RGB |
| Transparent colors | RGBA or HSLA |
| Easy color adjustments | HSL |
| Theme-friendly transparent colors | HSLA |
| A fully transparent color | `transparent` |
| Consistent component colors | `currentColor` |

> 💡 **Remember:** There is no single "best" color format. The best choice depends on your project's requirements and the level of flexibility you need.


---


## References

The following resources provide comprehensive documentation and examples for CSS colors:

- **MDN Web Docs** – CSS Colors
- **MDN Web Docs** – `<color>` Data Type
- **MDN Web Docs** – CSS Color Values
- **W3Schools** – CSS Colors
- **W3C CSS Color Module Level 4**

### Recommended Reading

If you'd like to explore CSS colors further, consider learning about:

- CSS Gradients
- CSS Color Functions
- CSS Custom Properties (Variables)
- Accessibility and Color Contrast
- Dark Mode and Theming