
---
# **Section-0: Introduction to CSS**

## 1. What is CSS?

- **CSS** stands for **Cascading Style Sheets**.
- It is used to control the **layout**, **style**, and **appearance** of a web page.
- CSS works alongside **HTML** to define the visual presentation of a webpage by styling the HTML elements (like text, images, and sections).

## 2. Why Use CSS?

- **Separation of Concerns**: CSS separates the content of the webpage (HTML) from its design, making it easier to maintain and update.
- **Consistency**: CSS allows you to apply the same styles to multiple pages of a website, ensuring a consistent look and feel.
- **Flexibility**: CSS provides a lot of flexibility, allowing you to adjust the layout, fonts, colors, spacing, and even animations without changing the HTML structure.
- **Responsiveness**: CSS helps in creating layouts that adapt to different screen sizes (e.g., mobile, tablet, desktop).

## 3. CSS Syntax

### Basic Structure of a CSS Rule:

```css
selector {
    property: value;
}
```

- **Selector**: The HTML element or group of elements you want to style (e.g., `h1`, `.container`, `#header`).
- **Property**: The CSS property you want to modify (e.g., `color`, `font-size`, `margin`).
- **Value**: The value you assign to the property (e.g., `red`, `16px`, `10px`).

#### Example:

```css
h1 {
    color: blue;
    font-size: 2em;
}
```

- This rule targets all `<h1>` elements and applies a **blue color** and a **font size of 2em**.

---

## 4. How CSS Can Be Applied

There are three ways to apply CSS to a webpage:

### 1. **Inline CSS** (directly within an HTML tag)

```html
<p style="color: blue;">This is a blue paragraph.</p>
```

- **Usage**: The `style` attribute applies styles directly to individual HTML elements.
- **Limitations**: Inline styles are not reusable and can clutter your HTML.

### 2. **Internal CSS** (within a `<style>` tag in the HTML document’s `<head>`)

```html
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
```

- **Usage**: CSS rules are written inside a `<style>` tag in the HTML `<head>`.
- **Limitations**: Styles apply only to the current document, so not reusable across multiple pages.

### 3. **External CSS** (via a linked CSS file)

```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

- **Usage**: The most common method. CSS is written in a separate `.css` file and linked to the HTML document.
- **Advantages**: This method promotes reusability, maintains cleaner HTML, and separates content from design.

---

## 5. CSS Selectors

CSS selectors are used to target HTML elements that you want to style. Some basic selectors include:

- **Universal Selector**: `*` targets all elements.
    
    ```css
    * {
        margin: 0;
        padding: 0;
    }
    ```
    
- **Type Selector**: Targets a specific HTML element (e.g., `p`, `h1`, `div`).
    
    ```css
    p {
        font-size: 16px;
    }
    ```
    
- **Class Selector**: Targets elements with a specific class (e.g., `.class-name`).
    
    ```css
    .container {
        width: 80%;
    }
    ```
    
- **ID Selector**: Targets a specific element with an ID (e.g., `#element-id`).
    
    ```css
    #header {
        background-color: lightblue;
    }
    ```
    
- **Descendant Selector**: Targets elements nested within another element.
    
    ```css
    div p {
        color: red;
    }
    ```
    

---

## 6. Common CSS Properties

- **Color and Background**:
    
    - `color`: Changes the color of text.
    - `background-color`: Sets the background color of an element.
    - `background-image`: Sets a background image.
- **Text Styling**:
    
    - `font-family`: Specifies the font type.
    - `font-size`: Defines the size of text.
    - `text-align`: Aligns text (e.g., `left`, `center`, `right`).
    - `line-height`: Adjusts the space between lines of text.
- **Box Model** (the structure of every element):
    
    - **`width`** and **`height`**: Set the dimensions of an element.
    - **`padding`**: Adds space inside an element, between the content and border.
    - **`border`**: Defines a border around an element.
    - **`margin`**: Adds space outside an element, between it and other elements.

---

## 7. Box Model

- The CSS **box model** is a fundamental concept that defines the layout structure of an element, consisting of:
    1. **Content**: The actual content of the element (text, images, etc.).
    2. **Padding**: Space around the content, inside the element.
    3. **Border**: A line surrounding the padding (optional).
    4. **Margin**: Space outside the border, separating the element from others.

```css
div {
    width: 300px;
    padding: 10px;
    border: 5px solid black;
    margin: 20px;
}
```

- In this example:
    - **Width** of content is 300px.
    - **Padding** adds 10px inside the box.
    - **Border** is 5px wide.
    - **Margin** adds 20px space outside the element.

---


# **Section-1: CSS Grid Layouts**
## Intro to Grids
### What is CSS Grid?

- **CSS Grid Layout** is a powerful two-dimensional layout system for the web, enabling control over both rows and columns.
- It simplifies the creation of complex layouts and enhances flexibility, allowing for more organized and efficient design when compared to traditional methods like floats or positioning.

---

### Basic Terminology

1. **Grid Container**: The parent element that defines the grid layout. It's created by applying `display: grid` to an element.
    
    ```css
    .container {
      display: grid;
    }
    ```
    
2. **Grid Items**: Direct children of the grid container, which will be placed within the grid cells.
    
3. **Grid Lines**: Horizontal and vertical lines that divide the grid, functioning as boundaries for positioning grid items.
    
4. **Grid Tracks**: The space between two adjacent grid lines, either for rows or columns.
    
5. **Grid Cells**: The smallest unit in the grid, formed by the intersection of a row and a column.
    
6. **Grid Areas**: The rectangular space between four grid lines, potentially spanning multiple cells.

---
### CSS Grid properties

|**Property**|**Description**|**Example**|
|---|---|---|
|**`display`**|Defines the container as a grid container.|`display: grid;`|
|**`grid-template-columns`**|Defines the number and size of columns in the grid.|`grid-template-columns: 100px 1fr 2fr;`|
|**`grid-template-rows`**|Defines the number and size of rows in the grid.|`grid-template-rows: 50px 200px;`|
|**`grid-template-areas`**|Defines named grid areas that can be used to position grid items.|`grid-template-areas: "header header" "main sidebar" "footer footer";`|
|**`grid-column`**|Specifies the position of a grid item within columns (start and end).|`grid-column: 1 / 3;`|
|**`grid-row`**|Specifies the position of a grid item within rows (start and end).|`grid-row: 1 / 2;`|
|**`grid-column-start`**|Defines the starting point of a grid item in the column.|`grid-column-start: 2;`|
|**`grid-column-end`**|Defines the ending point of a grid item in the column.|`grid-column-end: 4;`|
|**`grid-row-start`**|Defines the starting point of a grid item in the row.|`grid-row-start: 1;`|
|**`grid-row-end`**|Defines the ending point of a grid item in the row.|`grid-row-end: 3;`|
|**`grid-area`**|A shorthand property for setting `grid-row-start`, `grid-column-start`, `grid-row-end`, and `grid-column-end`.|`grid-area: 1 / 1 / 3 / 4;`|
|**`grid-auto-columns`**|Defines the size of implicitly created columns.|`grid-auto-columns: 100px;`|
|**`grid-auto-rows`**|Defines the size of implicitly created rows.|`grid-auto-rows: 50px;`|
|**`grid-auto-flow`**|Specifies the auto-placement algorithm, determining how grid items are placed when they are not explicitly placed.|`grid-auto-flow: row;`|
|**`justify-items`**|Aligns all items horizontally within their grid area.|`justify-items: center;`|
|**`align-items`**|Aligns all items vertically within their grid area.|`align-items: start;`|
|**`justify-self`**|Aligns a single grid item horizontally within its grid area.|`justify-self: stretch;`|
|**`align-self`**|Aligns a single grid item vertically within its grid area.|`align-self: center;`|
|**`gap`**|Defines the gap (space) between grid rows and columns.|`gap: 20px;`|
|**`row-gap`**|Defines the gap between rows.|`row-gap: 10px;`|
|**`column-gap`**|Defines the gap between columns.|`column-gap: 15px;`|
|**`justify-content`**|Aligns the entire grid container horizontally when it has extra space.|`justify-content: center;`|
|**`align-content`**|Aligns the entire grid container vertically when it has extra space.|`align-content: space-between;`|
|**`place-items`**|A shorthand for `align-items` and `justify-items`.|`place-items: center;`|
|**`place-self`**|A shorthand for `align-self` and `justify-self`.|`place-self: end;`|
|**`grid`**|A shorthand for defining `grid-template-columns`, `grid-template-rows`, `grid-template-areas`, and `gap`.|`grid: 1fr 2fr / auto 200px;`|
|**`grid-template`**|A shorthand for defining `grid-template-rows`, `grid-template-columns`, and `grid-template-areas`.|`grid-template: 100px 1fr / auto;`|
|**`grid-column-gap`**|Same as `column-gap`.|`grid-column-gap: 20px;`|
|**`grid-row-gap`**|Same as `row-gap`.|`grid-row-gap: 10px;`|

---

#### Key Points:

- **`grid-template-columns`** and **`grid-template-rows`** define the grid structure.
- **`grid-column`**, **`grid-row`** define item positions.
- **`grid-template-areas`** is useful for naming grid areas for more readable layouts.
- **Alignment properties** (like **`justify-items`**, **`align-items`**, **`justify-self`**, **`align-self`**) control alignment within grid items.
- **`gap`** defines spacing between rows and columns.
- **Shorthand properties** like **`grid`**, **`grid-template`**, **`place-items`**, and **`place-self`** help simplify your CSS.

---
### Creating a Basic Grid

- To create a grid, apply `display: grid` to a container element.

```css
.container {
  display: grid;
}
```

---

### Defining Columns and Rows

- Use `grid-template-columns` and `grid-template-rows` to define the structure of the grid.

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 100px; /* 3 columns */
  grid-template-rows: 50px 150px; /* 2 rows */
}
```

- You can also use fractional units (`fr`) for responsive layouts:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr; /* 2 columns, the second takes twice the space */
}
```

---

### Grid Gap

- **`grid-gap`** or **`gap`** defines the space between grid items (both rows and columns).

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 20px; /* 20px gap between grid items */
}
```

---

### Placing Grid Items

- By default, grid items will flow into the grid. However, you can control their positioning with:
    
    - **`grid-column`**: Specifies the start and end of a grid item along the columns.
    - **`grid-row`**: Specifies the start and end of a grid item along the rows.

```css
.item {
  grid-column: 1 / 3; /* Spans from column 1 to column 3 */
  grid-row: 1 / 2; /* Spans from row 1 to row 2 */
}
```

- You can also use shorthand for both row and column placement:

```css
.item {
  grid-area: 1 / 1 / 2 / 3; /* shorthand for grid-row-start, grid-column-start, grid-row-end, grid-column-end */
}
```

---

### Naming Grid Areas

- You can name specific grid areas and assign grid items to those areas by referring to their names.

```css
.container {
  display: grid;
  grid-template-areas: 
    "header header header"
    "main main sidebar"
    "footer footer footer";
}

.header {
  grid-area: header;
}
.main {
  grid-area: main;
}
.sidebar {
  grid-area: sidebar;
}
.footer {
  grid-area: footer;
}
```

---

## Responsive Grid Layouts
### Media Queries
- Use `@media` queries to create responsive layouts. You can adjust the number of columns or their size based on the screen size.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

@media (max-width: 600px) {
  .container {
    grid-template-columns: 1fr; /* Single column layout on small screens */
  }
}
```

---

### Auto-fill and Auto-fit

- **`auto-fill`**: Fills the grid with as many columns as can fit in the container.
- **`auto-fit`**: Similar to `auto-fill`, but the last column stretches to fill the remaining space if there’s less content.

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

---

### Implicit Grid

- If grid items exceed the defined rows or columns, they will be placed in an implicit grid. You can control the implicit grid with `grid-auto-rows` and `grid-auto-columns`.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 100px; /* Automatically adds rows of 100px when more items are present */
}
```

---

### Aligning Items within Grid Cells

- Use these properties to control the alignment of items within their grid cells:
    
    - **`justify-items`**: Aligns items horizontally within their grid cell.
    - **`align-items`**: Aligns items vertically within their grid cell.
    - **`justify-self`**: Aligns a specific grid item horizontally within its cell.
    - **`align-self`**: Aligns a specific grid item vertically within its cell.

```css
.container {
  display: grid;
  justify-items: center; /* Horizontally centers all items */
  align-items: center;   /* Vertically centers all items */
}
```

---

### Grid Layout vs Flexbox

- **CSS Grid**: Best suited for two-dimensional layouts (both rows and columns).
- **Flexbox**: Ideal for one-dimensional layouts (either rows OR columns).

---

## Additional Practical Application: CSS Grid Layout Example

#### Basic Layout Structure Using Grid**

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 300px 1fr;
    grid-template-rows: auto auto 1fr auto;
    grid-template-areas: 
        "header header"
        "navbar navbar"
        "sidebar main"
        "sidebar footer";
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

header, nav, main, footer, aside, section, article {
    border: 3px dotted black;
    padding: 1em;
}

header {
    grid-area: header;
    background-color: blueviolet;
    color: #fff;
    padding: 1em;
    text-align: center;
}

nav {
    top: 0;
    position: sticky;
    grid-area: navbar;
    padding: 0.5em;
    background-color: lightblue;
    display: flex;
    align-items: center;
}

aside {
    height: calc(100vh - 40px);
    top: 40px;
    position: sticky;
    grid-area: sidebar;
    background-color: grey;
    padding: 1em;
}

main {
    grid-area: main;
    background-color: lightgreen;
    padding: 1em;
}

footer {
    grid-area: footer;
    background-color: lightcoral;
    padding: 1em;
    text-align: center;
}

@media(max-width: 800px) {
    body {
        grid-template-columns: 1fr;
    }

    nav button {
        display: block;
    }

    aside {
        position: fixed;
        width: 300px;
        display: none;
    }

    .show {
        display: block;
    }
}
```


# **Section-2: CSS Flexbox Layout**

## **1. Global Reset and Box-Sizing**

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

- **Purpose**:
    - Resets margin and padding to eliminate default browser styling.
    - `box-sizing: border-box;` ensures padding and borders are included in an element's total width and height.

---

## **2. Layout Structure**

### Targeted HTML Elements:

```css
header, nav, main, footer, 
aside, section, article {
    border: 3px dotted black;
    padding: 1em;
}
```

- **Border**: Adds a dotted outline to visualize the structure during development.
- **Padding**: Provides space inside the elements for better readability.

---

## **3. Flexbox Layout for the Body**

### CSS Code:

```css
body {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    font-family: Arial, sans-serif;
    line-height: 1.6;
}
```

- **Properties Explained**:
    - `min-height: 100vh;` ensures the body occupies the full viewport height.
    - **Flexbox Layout**:
        - `display: flex;` applies flexbox to the body for a flexible layout.
        - `flex-direction: column;` arranges the elements in a vertical stack (header on top, footer on bottom).
    - **Font Styling**:
        - `font-family: Arial, sans-serif;` sets a clean and readable font.
        - `line-height: 1.6;` improves text spacing.

---

## **4. Section-Specific Styling**

### **4.1) Header**

```css
header {
    background-color: blueviolet;
    color: #fff;
    padding: 1em;
    text-align: center;
    flex: 0 1 auto;
}
```

- **Flexbox**: `flex: 0 1 auto;` ensures the header doesn't grow or shrink, and it takes only the space required for its content.
- **Background**: Uses a vibrant **blueviolet** background with white text for emphasis.

### **4.2) Navigation (Navbar)**

```css
nav {
    padding: 0.5em;
    background-color: lightblue;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex: 0 1 auto;
}
```

- **Flexbox**:
    - `display: flex;` enables flexbox.
    - `justify-content: space-between;` distributes items evenly with space between them.
    - `align-items: center;` vertically centers the items within the navbar.
- **Background**: Styled with **light blue** for the navbar.

### **4.3) Sidebar**

```css
aside {
    background-color: grey;
    padding: 1em;
    flex: 0 1 300px;
}
```

- **Flexbox**: `flex: 0 1 300px;` allows the sidebar to have a fixed width of 300px while still being flexible enough for different layouts.
- **Background**: Uses a neutral **grey** color for the sidebar.

### **4.4) Main Content**

```css
main {
    background-color: lightgreen;
    padding: 1em;
    flex: 1 1 auto;
}
```

- **Flexbox**: `flex: 1 1 auto;` makes the main content area flexible, taking up the remaining space in the layout.
- **Background**: Styled with a light **green** background.

### **4.5) Footer**

```css
footer {
    background-color: lightcoral;
    padding: 1em;
    text-align: center;
    flex: 0 1 auto;
}
```

- **Flexbox**: `flex: 0 1 auto;` ensures the footer only takes up the necessary space and doesn't grow or shrink.
- **Background**: Styled with a **light coral** background for contrast.

---

## **5. Utility Classes**

```css
.empty {
    height: 250px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 3px solid lightcoral;
    margin: 0.3em;
}
```

- **Purpose**: Placeholder element styled with:
    - **Flexbox** for centering content both horizontally and vertically.
    - **Borders** and margins for visibility.

---

## **6. Responsive Design**

### Media Query for Small Screens (`max-width: 800px`):

```css
@media(max-width: 800px) {
    body {
        flex-direction: column;
    }

    nav button {
        display: block;
    }

    aside {
        display: none;
    }

    .show {
        display: block;
    }
}
```

- **Adjustments**:
    - **Body Layout**: Switches to a **column layout** for small screens to stack elements.
    - **Navbar**: Navigation buttons become visible for mobile screens (`display: block;`).
    - **Sidebar**: Hidden by default but can be shown when `.show` class is added.

---

## **Key Concepts Covered**

- **CSS Flexbox**: Using `display: flex;` for layout and positioning.
- **Flex Properties**: `flex`, `justify-content`, and `align-items` for controlling item distribution.
- **Responsive Design**: Media queries for adapting layout on small screens.
- **Utility Classes**: Modular design to reuse styling.

---
---
# **Section-3: CSS Transitions & Animations**

## **1. CSS Transitions**

### Example:

```css
button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    border: none;
    transition: background-color 0.3s ease, transform 0.3s ease;
}

button:hover {
    background-color: green;
    transform: scale(1.1);
}
```

- **Purpose**: Transitions allow you to gradually change property values over a specified duration.
- **`transition` Property**:
    - `background-color 0.3s ease`: Changes the background color over 0.3 seconds with an "ease" timing function.
    - `transform 0.3s ease`: Scales the button up by 10% on hover.
- **Hover Effect**: On hover, the button's background color changes to green, and it scales up.

---

## **2. CSS Animations**

### Example:

```css
@keyframes slide {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

.box {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    animation: slide 1s ease-out forwards;
}
```

- **Purpose**: Animations allow for more complex and continuous effects compared to transitions.
- **`@keyframes`**:
    - Defines the stages of an animation (e.g., `from` and `to`).
    - `transform: translateX(-100%);` moves the element off-screen initially.
    - `transform: translateX(0);` brings the element to its final position.
- **Animation Properties**:
    - `slide 1s ease-out`: Specifies the animation name, duration, and timing function.
    - `forwards`: Retains the final state of the animation.

---

## **3. Responsive Typography**

### Example:

```css
body {
    font-size: 16px;
}

h1 {
    font-size: 2em;
}

@media(max-width: 768px) {
    body {
        font-size: 14px;
    }

    h1 {
        font-size: 1.5em;
    }
}
```

- **Purpose**: Responsive typography adjusts font sizes based on screen size to improve readability on smaller screens.
- **Base Font Size**: Set to 16px for the body text.
- **Media Query**: For screens smaller than 768px, the font size is reduced to 14px for the body and 1.5em for the `<h1>` heading.

---

## **4. Flexbox for Centering**

### Example:

```css
.center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.box {
    width: 200px;
    height: 100px;
    background-color: coral;
}
```

- **Purpose**: Flexbox can be used to center content both horizontally and vertically.
- **`justify-content: center;`**: Centers items horizontally.
- **`align-items: center;`**: Centers items vertically.
- **`height: 100vh;`**: Ensures the container occupies the full height of the viewport.

---

## **5. Box Shadows and Hover Effects**

### Example:

```css
.box {
    width: 200px;
    height: 200px;
    background-color: lightblue;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: box-shadow 0.3s ease;
}

.box:hover {
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}
```

- **Purpose**: Box shadows can add depth and dimension to elements.
- **Hover Effect**: On hover, the shadow grows, making the element appear lifted.
- **Transition**: Smooth transition of the shadow effect when the element is hovered over.

---

## **6. Sticky Positioning**

### Example:

```css
header {
    position: sticky;
    top: 0;
    background-color: lightseagreen;
    padding: 10px;
    color: white;
}
```

- **Purpose**: `position: sticky;` allows an element to "stick" to the top of the viewport when scrolling.
- **`top: 0;`**: Defines how far from the top the element should stick.
- **Background**: A sticky header with a **lightseagreen** background that remains visible at the top of the page.

---

## **7. Custom Scrollbars**

### Example:

```css
::-webkit-scrollbar {
    width: 12px;
}

::-webkit-scrollbar-thumb {
    background-color: darkgray;
    border-radius: 10px;
}

::-webkit-scrollbar-track {
    background-color: lightgray;
}
```

- **Purpose**: Customizes the appearance of scrollbars in WebKit-based browsers.
- **`::-webkit-scrollbar`**: Controls the width of the scrollbar.
- **`::-webkit-scrollbar-thumb`**: Styles the thumb (the draggable part of the scrollbar).
- **`::-webkit-scrollbar-track`**: Styles the track (the background area the thumb moves along).

---

## **8. Custom Fonts with @font-face**

### Example:

```css
@font-face {
    font-family: 'MyCustomFont';
    src: url('path/to/font.woff2') format('woff2'),
         url('path/to/font.woff') format('woff');
}

body {
    font-family: 'MyCustomFont', sans-serif;
}
```

- **Purpose**: `@font-face` allows you to load custom fonts on your website.
- **`src`**: Specifies the path to the font file in different formats (e.g., WOFF2 and WOFF).
- **Fallback Font**: If the custom font cannot be loaded, the browser will fall back to the system’s sans-serif font.

---

## **Key Concepts Covered**

- **CSS Transitions**: Gradual changes in property values.
- **CSS Animations**: Complex, keyframe-based animations for dynamic effects.
- **Responsive Typography**: Adjusting font sizes for various screen sizes.
- **Flexbox**: Using flexbox for centering content and layout adjustments.
- **Sticky Positioning**: Making elements stick to the viewport while scrolling.
- **Custom Scrollbars**: Styling the scrollbars for a more personalized user experience.
- **Custom Fonts**: Implementing external fonts with `@font-face`.

---
---
