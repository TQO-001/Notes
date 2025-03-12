
---
# **Section-0: Introduction to CSS**

## **1. What is CSS?**

- **CSS** stands for **Cascading Style Sheets**.
- It is used to control the **layout**, **style**, and **appearance** of a web page.
- CSS works alongside **HTML** to define the visual presentation of a webpage by styling the HTML elements (like text, images, and sections).

## **2. Why Use CSS?**

- **Separation of Concerns**: CSS separates the content of the webpage (HTML) from its design, making it easier to maintain and update.
- **Consistency**: CSS allows you to apply the same styles to multiple pages of a website, ensuring a consistent look and feel.
- **Flexibility**: CSS provides a lot of flexibility, allowing you to adjust the layout, fonts, colors, spacing, and even animations without changing the HTML structure.
- **Responsiveness**: CSS helps in creating layouts that adapt to different screen sizes (e.g., mobile, tablet, desktop).

## **3. CSS Syntax**

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

## **4. How CSS Can Be Applied**

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

## **5. CSS Selectors**

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

## **6. Common CSS Properties**

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

## **7. Box Model**

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

## **8. Comments in CSS**

- Comments in CSS allow you to add notes to your code without affecting the styling.

```css
/* This is a single-line comment */

/* 
   This is a multi-line comment
   that spans multiple lines
*/
```

---

## **9. CSS Cascading and Specificity**

- **Cascading**: CSS follows a specific order of precedence (cascading). When multiple rules apply to the same element, the most specific rule wins.
- **Specificity**: Rules with more specific selectors (e.g., ID selectors) override rules with less specific selectors (e.g., class selectors).

---

## **Key Concepts Covered**

- **CSS**: A language used to style and design HTML elements.
- **CSS Syntax**: Structure of selectors, properties, and values.
- **Selectors**: Ways to target HTML elements for styling.
- **CSS Properties**: Common properties for color, layout, typography, and more.
- **Box Model**: Understanding how the space around elements is calculated.
- **Comments**: Writing comments for clarity and maintenance.

---
---
# **Section-1: CSS Grid Layout**

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

## **3. Grid Layout for the Body**

### CSS Code:

```css
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
```

- **Properties Explained**:
    - `min-height: 100vh;` ensures the body occupies the full viewport height.
    - **Grid Definitions**:
        - `grid-template-columns: 300px 1fr;`  
            Creates two columns: a fixed-width sidebar (`300px`) and a flexible main content area (`1fr`).
        - `grid-template-rows: auto auto 1fr auto;`  
            Defines rows for header, navbar, content, and footer. Rows automatically adjust height (`auto`) except for the main content, which fills the remaining space (`1fr`).
        - `grid-template-areas`: Names sections for easy placement in the grid.
    - **Font Styling**:
        - `font-family: Arial, sans-serif;` sets a clean and readable font.
        - `line-height: 1.6;` improves text spacing.

---

## **4. Section-Specific Styling**

### **4.1) Header**

```css
header {
    grid-area: header;
    background-color: blueviolet;
    color: #fff;
    padding: 1em;
    text-align: center;
}
```

- Assigned to the **`header`** grid area.
- Uses a vibrant **blueviolet background** with white text.

### **4.2) Navigation (Navbar)**

```css
nav {
    top: 0;
    position: sticky;
    grid-area: navbar;
    padding: 0.5em;
    background-color: lightblue;
    display: flex;
    align-items: center;
}
nav button {
    display: none;
}
```

- Positioned **sticky** to remain at the top during scrolling.
- Styled with **light blue background** and uses `flexbox` for alignment.
- Navigation buttons (`nav button`) are hidden by default.

### **4.3) Sidebar**

```css
aside {
    height: calc(100vh - 40px);
    top: 40px;
    position: sticky;
    align-self: start;
    grid-area: sidebar;
    background-color: grey;
    padding: 1em;
}
```

- Sticky positioning ensures the sidebar stays visible while scrolling.
- Height is calculated dynamically to exclude 40px (possibly for navbar).

### **4.4) Main Content**

```css
main {
    grid-area: main;
    background-color: lightgreen;
    padding: 1em;
}
```

- Flexible grid area for primary content.
- Styled with a light green background.

### **4.5) Footer**

```css
footer {
    grid-area: footer;
    background-color: lightcoral;
    padding: 1em;
    text-align: center;
}
```

- Placed at the bottom with a light coral background.

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
    - **Flexbox** for centering content.
    - **Borders** and margins for visibility.

---

## **6. Responsive Design**

### Media Query for Small Screens (`max-width: 800px`):

```css
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

- **Adjustments**:
    - **Body Layout**: Single-column grid for smaller screens (`grid-template-columns: 1fr;`).
    - **Navbar**: Navigation buttons become visible (`display: block;`).
    - **Sidebar**:
        - Positioned **fixed** for mobile navigation.
        - Hidden by default but displayed when `.show` is added.

---

## **Key Concepts Covered**

- CSS Grid: Defining areas, responsive grid adjustments.
- Positioning: Sticky and fixed positioning for dynamic layouts.
- Flexbox: Used for centering and aligning.
- Responsive Design: Media queries for small screen adaptations.
- Utility Classes: Modular design for reusability.

---
---
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
