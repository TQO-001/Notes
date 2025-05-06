# CSS Essentials Cheat Sheet

---

## 1️⃣ CSS Syntax

- **Selector** `{ property: value; }`
- Multiple selectors: `,`
- Comments: `/* comment */`

---

## 2️⃣ Box Model
> Margin → Border → Padding → Content.

Every HTML element is a **box** made up of:

| Layer     | Description                                           |
| --------- | ----------------------------------------------------- |
| `margin`  | Space **outside** the element border.                 |
| `border`  | Surrounds the padding + content.                      |
| `padding` | Space **inside** the border, around the content.      |
| `content` | The actual text, image, or other data inside the box. |
![[box-model.png]]

### 🔍 **Key Notes:**
- **Total width =** `margin + border + padding + content`\
- **Default Box Model:**  
    Width/height only includes the **content** by default. Padding and border are _added on top._
- **Better practice:**  
    `box-sizing: border-box;` tells the browser to **include padding & border within the width/height.**  
    This makes layouts much easier to handle.
- **Margin collapsing:**  
    Vertical margins of block elements can **collapse** (e.g., two `p` elements stacked will share margin).

### 💡 **Example:**
```css
.box {   
	width: 200px;   
	padding: 20px;   
	border: 5px solid black;   
	margin: 30px; 
}
```

If no `box-sizing`, the total width =  `200 (content) + 40 (padding) + 10 (border) = 250px`

---

## 3️⃣ Display Types
CSS has different **display values** that control how elements behave:

|Type|Behavior|
|---|---|
|`block`|Takes full width, starts on a new line.|
|`inline`|Takes only as much width as needed; **no block-level styling** (e.g., width).|
|`inline-block`|Like `inline`, but allows width/height.|
|`none`|Hides the element (removes from flow).|
|`flex`|Flexbox container.|
|`grid`|Grid container.|

>📝 **Important:**  The **display** property is the **foundation** for Flexbox, Grid, and many modern layouts.

### 🧩 Additional Details on Each Display Type:

#### 1. **`block`**
- Examples: `<div>`, `<section>`, `<p>`
- Can set width, height, margin, padding.
- Stacks vertically by default.

#### 2. **`inline`**
- Examples: `<span>`, `<a>`, `<strong>`
- Cannot set box-model properties like width/height/margin-top or margin-bottom.
- Respects surrounding text flow.

#### 3. **`inline-block`**
- Best of both worlds:
    - Behaves like `inline` in flow.
    - Allows `block` features (width, height).
- Useful for buttons, labels, or inline forms.

#### 4. **`none`**
- Completely removes the element from the layout and accessibility tree (unless hidden via `visibility: hidden`, which keeps space).
- Often used with JavaScript toggles.

#### 5. **`flex`**
- Turns the container into a **flex formatting context**.
- Children become **flex items**, controlled by properties like `justify-content`, `align-items`, `flex-wrap`, etc.
- Ideal for 1-dimensional layouts.

#### 6. **`grid`**
- Turns the container into a **grid formatting context**.
- Children are placed into **rows and columns**.
- Powerful for 2D layouts.

---

### 🧠 Pro Tips:

- Default `display` types depend on the HTML element (e.g., `div` is `block`, `span` is `inline`).
- Changing `display` can completely alter layout behavior — it's often the first thing to inspect when debugging layout issues.
- Use browser dev tools (e.g., Chrome's "Inspect") to visualize an element’s box and its display type.


---
## 4️⃣ Flexbox Basics
Flexbox is designed for **1D layouts** (row or column).
- Set parent: `display: flex;`
- **Main axis:** by default horizontal.
- **Cross axis:** perpendicular to main axis.

### **Key Properties (Parent/Container):**

- `flex-direction`:  Sets the main axis:
    - `row` (default)
    - `column`
    - `row-reverse` / `column-reverse`
    
- `justify-content`:  Aligns items along the **main axis.**  
    Values: `flex-start`, `center`, `space-between`, etc.
    
- `align-items`:  Aligns items along the **cross axis.**  
    Values: `stretch`, `center`, `flex-start`, etc.
    
- `flex-wrap`:  Should items wrap if they don't fit?  
    `nowrap` (default), `wrap`

### **Key Properties (Child/Item):**

- `flex-grow`:  How much the item should grow relative to others.
    
- `flex-shrink`:  How much it should shrink.
    
- `flex-basis`:  The starting size before grow/shrink.
    
- `align-self`:  Overrides the container's `align-items`.
    

---

### 💡 **Example:**

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}
```

---
## 5️⃣ Grid Basics
Grid is designed for **2D layouts** (rows + columns), enabling control over both rows and columns.

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

Let you apply CSS based on **screen width (or other features).**

```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

- Typical breakpoints:
    
    - `320px` - `480px` (mobile)
    - `768px` (tablet)
    - `1024px` (desktop)
    - `1440px+` (large screens)

### 🔄 Fluid Layout Tips
- Use relative units for scalable sizes: `%`, `vw/vh`, `em/rem` .
- Flexbox/Grid handle responsiveness **naturally.**

---

## 7️⃣ Positioning

| Type       | Description                                                                        |
| ---------- | ---------------------------------------------------------------------------------- |
| `static`   | Default; Follows normal document flow.                                             |
| `relative` | Offset **relative to itself.** Moves but keeps its space.                          |
| `absolute` | Positioned relative to **nearest positioned ancestor. ** Removed from normal flow. |
| `fixed`    | Stays in place **relative to viewport.**                                           |
| `sticky`   | Switches between relative/fixed depending on scroll.                               |

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
Typography is key for **readability and design:**

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
## ✨ **Wrap-up:**

- Box model and display types = **foundation** of CSS.
- Flexbox = **1D layout** (great for navs, lists, toolbars).
- Grid = **2D layout** (perfect for full page or cards).
- Media queries = **make it responsive.**
- Positioning = **fine-tune placement.**
- Typography = **boosts design quality.**
