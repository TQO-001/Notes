# CSS Essentials Cheat Sheet

---

## 1️⃣ CSS Syntax

- **Selector** `{ property: value; }`
- Multiple selectors: `,`
- Comments: `/* comment */`

---

## 2️⃣ Box Model
Every HTML element is a **box** made up of:

| Layer     | Description                                           |
| --------- | ----------------------------------------------------- |
| `margin`  | Space **outside** the element border.                 |
| `border`  | Surrounds the padding + content.                      |
| `padding` | Space **inside** the border, around the content.      |
| `content` | The actual text, image, or other data inside the box. |
![[box-model.png]]

### 📦 Key Concepts

- **Total width =** `margin + border + padding + content`
- Use `box-sizing: border-box;` to include padding + border **inside** the width/height.
- You can set:
    
    - `margin: 10px;` (all sides)
    - `margin: 10px 20px;` (top-bottom / left-right)
    - `margin: 10px 15px 20px 25px;` (top, right, bottom, left)

#### ➕ Shorthand:

```css
padding: 10px 20px;  /* top-bottom 10px, left-right 20px */
border: 1px solid #000;
```

---

## 3️⃣ Display Types

|Type|Behavior|
|---|---|
|`block`|Takes full width, starts on a new line.|
|`inline`|Takes only as much width as needed; **no block-level styling** (e.g., width).|
|`inline-block`|Like `inline`, but allows width/height.|
|`none`|Hides the element (removes from flow).|
|`flex`|Flexbox container.|
|`grid`|Grid container.|

---

## 4️⃣ Flexbox Basics

- Set parent: `display: flex;`
- **Main axis:** by default horizontal.
- **Cross axis:** perpendicular to main axis.

### Key Properties (Parent)

- `flex-direction`: `row` | `row-reverse` | `column` | `column-reverse`
- `justify-content`: aligns along **main axis.**
    - `flex-start` | `center` | `space-between` | `space-around` | `space-evenly`
- `align-items`: aligns along **cross axis.**
    - `stretch` | `center` | `flex-start` | `flex-end`
- `flex-wrap`: `nowrap` (default) | `wrap` | `wrap-reverse`

### Child Props

- `flex-grow`: how much to **grow.**
- `flex-shrink`: how much to **shrink.**
- `flex-basis`: **initial size.**
- `align-self`: override parent's `align-items`.

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

## 5️⃣ Grid Basics
- **CSS Grid Layout** is a powerful two-dimensional layout system for the web, enabling control over both rows and columns.
- Set parent: `display: grid;`
- Define rows/columns:
    - `grid-template-columns: 1fr 2fr;`
    - `grid-template-rows: 100px auto;`
- Place items:
    - `grid-column: 1 / 3;`
    - `grid-row: 2 / 4;`
- Gap:
    - `gap: 10px;` (or `row-gap` / `column-gap`)

Example:

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
```

---

## 6️⃣ Responsive Design

### 📱 Media Queries

- Syntax:

```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

- Typical breakpoints:
    
    - `320px` (mobile)
    - `768px` (tablet)
    - `1024px` (desktop)
    - `1440px+` (large screens)

### 🔄 Fluid Layout Tips

- Use `%`, `vw/vh`, `em/rem` for scalable sizes.
- Flexbox/Grid handle responsiveness **naturally.**

---

## 7️⃣ Positioning

|Type|Description|
|---|---|
|`static`|Default; normal flow.|
|`relative`|Offset **relative to itself.**|
|`absolute`|Positioned relative to **nearest positioned ancestor.**|
|`fixed`|Stays in place **relative to viewport.**|
|`sticky`|Switches between `relative` & `fixed` when crossing a threshold.|

Example:

```css
.box {
  position: absolute;
  top: 20px;
  left: 50px;
}
```

**Z-index:** controls stacking.

---

## 8️⃣ Typography Basics

|Property|Usage|
|---|---|
|`font-size`|Size of text (e.g., `16px`, `1rem`, `1.5em`).|
|`line-height`|Space between lines (e.g., `1.5`, `150%`).|
|`font-weight`|Thickness (`400` = normal, `700` = bold).|
|`font-family`|Choose fonts (`'Roboto', sans-serif`).|
|`letter-spacing`|Space between letters.|
|`text-align`|Align text (`left`, `center`, `right`, `justify`).|
|`text-transform`|`uppercase`, `lowercase`, `capitalize`.|

Example:

```css
p {
  font-size: 1rem;
  line-height: 1.6;
  font-weight: 400;
  text-align: justify;
}
```

---

✅ **Bonus Tips:**

- **Cascade & Specificity:** Later rules override earlier ones; more specific selectors win.
- **Units:** `rem` = relative to root; `em` = relative to parent.

---
