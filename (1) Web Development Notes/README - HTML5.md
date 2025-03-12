
<table>
 <tr>
  <td><strong>Text Editors</strong></td>
  <td><a href='https://code.visualstudio.com/'>VS Code</a></td>
  <td><a href='https://www.sublimetext.com/'>Sublimetext</a></td>
  <td><a href='https://atom.io/'>Atom</a></td>
 </tr>
</table>
---
---
# Section-0: HTML Document Summary
---
## `<html>`
- **Purpose**: The root element that wraps all other HTML elements. The tag shows up at the beginning and end of an HTML document (known as the root element). It indicates that the webpage is written in HTML5.
- **Attributes**: 
	  - `lang`: Specifies the language of the document.
#### **Example**: 
  ```html
<html lang="en">
  ...
</html>
  ```
---
## `<head>`  

- **Purpose**: Contains metadata about the HTML document (e.g., links to stylesheets and rarely scripts, meta data, title tag).  
- **Elements inside `<head>`**:  
	  - `<meta>`: Defines metadata like character encoding, viewport settings, and SEO information.  
	  - `<link>`: Connects external resources (e.g., stylesheets, icons).  
	  - `<title>`: Defines the title displayed on the browser tab.  
#### **Example**:
```HTML
<head>
	<!-- meta tag -->
	<meta attribute="value">
	<!-- link tag -->
	<link rel="stylesheet" src="Styles.css">
	<!-- title tag -->
	<title>title name</title>
</head>
```
---
## **Basic Structure: Example**
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
	<!-- Character encoding for the document -->
    <meta charset="UTF-8"> 
	<!-- Makes the page responsive on mobile devices -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- The title that appears in the browser tab -->
    <title>Document Title</title> 
</head>
<body>
    <!-- Content of the page goes here -->
</body>
</html>

```

---
---
# Section-1:  HTML Document Information
## **Section-1.1**`<base>`

- **Purpose**: Specifies a base URL (for example: www.YourSite.com) for all relative URLs in a document (especially if you have many internal links). This affects the resolution of relative links (like images, scripts, and hyperlinks) to be relative to the base URL set by the `<base>` tag.

- **Attributes**:
	- **`href`**: Defines the base URL for all relative links. If not specified, the default is the URL of the document itself.
	- **`target`**: Specifies the default target for links and forms (e.g., `_blank`, `_self`, `_parent`, `_top`).

- **Behaviour**: When the `<base>` tag is used, all relative URLs (e.g., `<a href="page.html">`) will be interpreted as relative to the base URL set by the `href` attribute, rather than the current URL.
#### **Example**: 
```html
<!-- Set base URL for all relative links -->
<base href="https://www.example.com/">

<!-- Set base URL and target for links -->
<base href="https://www.example.com/" target="_blank">
```

- **Notes**:
    - Only one `<base>` tag should be used in a document. Placing multiple `<base>` tags can cause unpredictable behavior.
    - It must be placed inside the `<head>` section of the HTML document.
---
## **Section-1.2**`<meta>`  

- **Purpose**: Provides metadata (additional information) about the page, such as the page's description, author, published date, keywords and other typically 'hidden' page information.

- **Attributes**:  
	  - **`charset`**: Specifies the character encoding for the document (e.g., `UTF-8`).  
	  - **`name`**: Defines the metadata name (e.g., `viewport`, `description`, `keywords`).  
	  - **`content`**: Provides the value for the metadata.  
	  - **`http-equiv`**: Used for HTTP headers (e.g., `refresh`, `content-type`).  

- **Examples**:  
  ```html
  <!-- Character Encoding -->
  <meta charset="UTF-8">

  <!-- Responsive Design -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- SEO Metadata -->
  <meta name="description" content="An awesome website about web development.">
  <meta name="keywords" content="HTML, CSS, JavaScript, Web Development">

  <!-- Refresh Page -->
  <meta http-equiv="refresh" content="30">
  ```

Let me explain these `<meta>` tags in more detail to help clarify their purpose:

---
### `<meta>`: A Closer Look  

- **What is `<meta>`?**  
  The `<meta>` tag provides metadata—information about the HTML document. This metadata does not appear on the page itself but is crucial for how browsers and search engines interpret and display the page.  

---
### Common `<meta>` Tags  

#### 1. **`<meta charset="UTF-8">`**  
- **Purpose**:  
  This specifies the character encoding used by the document, ensuring that all characters (including special symbols, emojis, or non-English characters) are correctly interpreted.  

- **Why we use it**:  
  - It ensures that the webpage supports a wide range of characters, including non-Latin scripts like Chinese, Arabic, and special symbols.  
  - `UTF-8` is the most widely used encoding because it's compatible with almost all languages and is the standard for modern web pages.  

- **Without it**:  
  Some characters might display incorrectly, resulting in "weird symbols" or "mojibake" (garbled text).  

- **Example Use Case**:  
  If your page has a non-English word like "Café", the `é` might not render correctly without this tag.  

---

#### 2. **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**  
- **Purpose**:  
  This tag helps your webpage be mobile-friendly by controlling how it is displayed and scaled on different devices (especially smaller screens like phones).  

- **Why we use it**:  
  - **`width=device-width`**: Ensures the page width matches the device's screen width. Without this, the page may zoom out and appear tiny on mobile devices.  
  - **`initial-scale=1.0`**: Sets the default zoom level to 100%, ensuring that users see the page at the correct scale when it loads.  

- **Without it**:  
  The page may look poorly scaled, requiring users to zoom in or scroll horizontally on mobile devices.  

- **Example Use Case**:  
  If you're building a website with a layout that adapts to screen sizes (responsive design), this tag ensures that the mobile experience matches your intentions.

---
### Key Takeaways

1. **`charset="UTF-8"`**: Ensures all text and symbols render properly. Always include this in modern webpages.  
2. **`name="viewport"`**: Optimizes your webpage for mobile devices, which is essential in modern web development.


---
## **Section-1.3**`<link>`  

- **Purpose**: Links external resources to the HTML document, such as stylesheets, icons, or preloading assets.  
- **Attributes**:  
  - **`rel`**: Specifies the relationship between the current document and the linked resource (e.g., `stylesheet`, `icon`).  
  - **`href`**: Specifies the URL of the linked resource.  
  - **`type`**: Defines the type of the linked content (e.g., `text/css`).  

- **Example**:  
  ```html
  <link rel="stylesheet" href="styles.css">
  <link rel="icon" href="favicon.ico" type="image/x-icon">
  <link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin="anonymous">
  ```

---
## **Section-1.4**`<title>`
- **Purpose**: Defines the document’s title, visible in the browser tab.
- **Example**: 
  ```html
  <title>My Awesome Site</title>
  ```

---
---
# Section-2: Body Element
## **Section-2.0**`<body>`
- **Purpose**: Wraps all content displayed on the page (headings, paragraphs, images, etc.).
#### **Example**: 
```html
<body>
	<h1>Welcome to My Website</h1>
	<p>This is a paragraph of text.</p>
</body>
```

---
---
## **Section-2.1: Document Structure**
### **Headings**

### `<h1>` to `<h6>`
- **Purpose**: Define different levels of headings, from the most important (`<h1>`) to least important (`<h6>`).
#### **Example**: 
  ```html
  <h1>Main Title</h1>
  <h2>Subheading</h2>
  <h6>Minor Heading</h6>
  ```

---
### **Line Breaks and Horizontal Rules**

### `<br>`
- **Purpose**: Inserts a line break (without a closing tag).
#### **Example**: 
  ```html
  This is a line<br>This is another line.
  ```

### `<hr>`
- **Purpose**: Creates a horizontal line separating content.
#### **Example**: 
  ```html
  <hr>
  ```
---
### **Layout and Semantics**

#### `<div>` and `<span>`
- **Purpose**: 
  - `<div>` is a generic block-level container used to denote a page section.
  - `<span>` is an inline container or block container, typically used for grouping styling elements.
#### **Example**: 
  ```html
  <div>This is a block-level element.</div>
  <span>This is an inline element.</span>
  ```

#### **Semantic Elements**

|Tag|Purpose|
|---|---|
|`<header>`|Defines the header section of a webpage|
|`<nav>`|Represents a navigation section|
|`<main>`|Represents the main content of a document|
|`<footer>`|Defines the footer section|
|`<article>`|Represents a self-contained piece of content, often used for articles or blog posts|
|`<aside>`|Represents content that is tangentially related to the main content (e.g., sidebars, pull quotes)|
|`<section>`|Represents a section of content, usually with a heading|
|`<details>`|Represents a disclosure widget from which the user can obtain additional information|
|`<dialog>`|Represents a dialog box or a window for interactions with the user|
|`<figcaption>`|Represents a caption for a `<figure>` element|
|`<figure>`|Represents content such as an image, chart, or other media along with its caption|
|`<mark>`|Represents text that has been highlighted or marked for reference or emphasis|
|`<summary>`|Represents a summary or heading for the `<details>` element, providing a summary for users|

These semantic elements help define the structure of a webpage more clearly, improving both accessibility and SEO by making the content more understandable to search engines and assistive technologies.

---
---
## **Section-2.2: Text (+ Formatting)**

### `<p>` (Paragraph)
- **Purpose**: Wraps text into a block-level paragraph.
#### **Example**: 
  ```html
  <p>This is a block of text.</p>
  ```

---
### Commonly Used Text Formatting Tags  

| **Tag**    | **Purpose**                              | **Example**                                           |
| ---------- | ---------------------------------------- | ----------------------------------------------------- |
| `<strong>` | Emphasizes text in bold.                 | `<strong>Important</strong>` → **Important**          |
| `<em>`     | Emphasizes text in italics.              | `<em>Italicized</em>` → *Italicized*                  |
| `<small>`  | Displays text in a smaller font size.    | `<small>Small text</small>` → Small text              |
| `<mark>`   | Highlights text.                         | `<mark>Highlighted</mark>` → <mark>Highlighted</mark> |
| `<del>`    | Represents deleted text (strikethrough). | `<del>Deleted</del>` → ~~Deleted~~                    |
| `<ins>`    | Represents inserted text (underlined).   | `<ins>Inserted</ins>` → Inserted                      |
| `<sub>`    | Formats text as subscript.               | `H<sub>2</sub>O` → H₂O                                |
| `<sup>`    | Formats text as superscript.             | `E = mc<sup>2</sup>` → E = mc²                        |

---

### Less Commonly Used Text Formatting Tags  

| **Tag**  | **Purpose**                                                             | **Example**                                                                                                                     |
| -------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `<b>`    | Makes text bold, without emphasis.                                      | `<b>Bold text</b>` → **Bold text**                                                                                              |
| `<i>`    | Makes text italic, without emphasis.                                    | `<i>Italic text</i>` → *Italic text*                                                                                            |
| `<u>`    | Underlines text.                                                        | `<u>Underlined</u>` → Underlined                                                                                                |
| `<abbr>` | Represents an abbreviation or acronym (tooltip displays full form).     | `<abbr title="Hypertext Markup Language">HTML</abbr>` → <abbr title="Hypertext Markup Language">HTML</abbr> (hover for tooltip) |
| `<cite>` | Indicates a citation or reference to a creative work.                   | `<cite>Book Title</cite>` → *Book Title*                                                                                        |
| `<code>` | Displays a piece of computer code.                                      | `<code>console.log('Hello');</code>` → `console.log('Hello');`                                                                  |
| `<kbd>`  | Represents user input (keyboard actions).                               | `<kbd>Ctrl + C</kbd>` → Ctrl + C                                                                                                |
| `<var>`  | Represents a variable in a mathematical or programming context.         | `<var>x</var> = 10` → *x* = 10                                                                                                  |
| `<s>`    | Represents text that is no longer accurate or relevant (strikethrough). | `<s>Old info</s>` → ~~Old info~~                                                                                                |

#### **Other Semantic Elements**

|Tag|Purpose|
|---|---|
|`<address>`|Represents contact information for a person or an organization|
|`<bdi>`|Represents text that might be formatted in a different direction from other text (Bi-directional isolation)|
|`<bdo>`|Allows overriding the current text direction (e.g., left-to-right or right-to-left)|
|`<data>`|Links a piece of content with a machine-readable value|
|`<dfn>`|Represents the defining instance of a term or phrase|
|`<figcaption>`|Represents a caption for a `<figure>` element|
|`<kbd>`|Represents user input (e.g., from a keyboard)|
|`<output>`|Represents the result of a calculation or user action|
|`<progress>`|Represents a progress bar for tasks that are in progress|
|`<time>`|Represents a specific time or a range of time|

---
## **Section-2.3: Links (+ Formatting)**
### `<a href="">`

- **Purpose**: Creates a hyperlink.
- **Attributes**:
    - `href`: URL to which the link points.
    - `target`: Determines how the link opens (`_blank` for a new tab).
#### **Example**:
```html
<a href="https://www.example.com" target="_blank">Visit Example</a>
```

#### `<a href="mailto:example@domain.com">`

- **Purpose**: Creates a link that opens the default email client with a new email addressed to the specified email address.
- **Example**:
    
    ```html
    <a href="mailto:example@domain.com">Send Email</a>
    ```

#### `<a href="tel://###-###-####">`

- **Purpose**: Creates a link that allows users to dial a phone number directly from the browser on supported devices.
- **Example**:
    
    ```html
    <a href="tel://555-123-4567">Call Us</a>
    ```

#### `<a href="#Header">`

- **Purpose**: Creates an anchor link that jumps to a specific section within the same page, where the target has the corresponding `id`.
- **Example**:
    
    ```html
    <a href="#Header">Go to Header Section</a>
    ```

#### `<a name="name">`

- **Purpose**: Creates an anchor at a specific point in the page that can be linked to from elsewhere in the same document. (This is an older method; it's recommended to use `id` instead of `name` for modern HTML.)
- **Example**:
    
    ```html
    <a name="section1">Section 1</a>
    ```
### **Additional Variations of `<a>`**

#### `<a href="javascript:void(0)">`

- **Purpose**: Creates a link that doesn’t navigate anywhere but can be used to trigger JavaScript code, often used with event listeners like `onclick`.
- **Example**:
    
    ```html
    <a href="javascript:void(0)" onclick="alert('Hello!')">Click Me</a>
    ```

#### `<a download="filename">`

- **Purpose**: Creates a link that, when clicked, downloads a file rather than navigating to it. The `download` attribute allows you to specify the filename for the download.
- **Example**:
    
    ```html
    <a href="example.pdf" download="NewFile.pdf">Download PDF</a>
    ```

#### `<a href="ftp://ftp.example.com/file">`

- **Purpose**: Creates a link to an FTP server, allowing the user to download or upload files via FTP protocol.
- **Example**:
    
    ```html
    <a href="ftp://ftp.example.com/file">Download via FTP</a>
    ```

#### `<a href="data:text/html;base64,...">`

- **Purpose**: Creates a link that triggers the download or opens a resource encoded in base64 format, often used for embedding images or other resources in a single HTML document.
- **Example**:
    
    ```html
    <a href="data:text/html;base64,PGh0bWw+...">Open Encoded File</a>
    ```

#### `<a href="sms:+1-800-555-5555">`

- **Purpose**: Creates a link that opens a default SMS app to send a message to a specific phone number.
- **Example**:
    
    ```html
    <a href="sms:+1-800-555-5555">Send SMS</a>
    ```

---

These variations expand the uses of the `<a>` tag beyond just linking to URLs, allowing you to trigger JavaScript functions, download files, and interact with other protocols like FTP and SMS. They’re especially useful for creating interactive and functional links.

---
## **Section-2.4: Lists**

HTML provides three main types of lists: unordered, ordered, and description lists. Lists are useful for displaying information in a structured format, such as navigation menus, instructions, or data groupings.
#### **1. Unordered Lists (`<ul>`)**
An unordered list displays items with bullets, circles, or squares as markers.

- **Syntax**:
  ```html
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
  ```

- **Attributes**:
  - `type`: Sets the bullet style (options: `disc`, `circle`, `square`), although CSS is generally preferred for styling.
#### **2. Ordered Lists (`<ol>`)**
Ordered lists display items with numerical or alphabetical order markers.

- **Syntax**:
  ```html
  <ol>
    <li>Step 1</li>
    <li>Step 2</li>
    <li>Step 3</li>
  </ol>
  ```

- **Attributes**:
  - `type`: Specifies the type of numbering (`1`, `A`, `a`, `I`, `i`).
  - `start`: Sets the starting value of the list.
  - `reversed`: Reverses the order (last item numbered as "1").
#### **3. Description Lists (`<dl>`)**
Description lists are used to pair terms and descriptions, often for glossaries or FAQs.

- **Syntax**:
  ```html
  <dl>
    <dt>Term 1</dt>
    <dd>Description for Term 1</dd>
    <dt>Term 2</dt>
    <dd>Description for Term 2</dd>
  </dl>
  ```

- **Elements**:
  - **`<dt>`**: Defines the term.
  - **`<dd>`**: Defines the description for the term.

---

---
---
## **Section-2.5: Media**

### **1. Images**

#### `<img>`
- **Purpose**: Embeds an image.
- **Attributes**: 
  - `src`: Path to the image.
  - `alt`: Text displayed if the image fails to load.
  - `width`, `height`: Set image dimensions.
- **Example**: 
  ```html
  <img src="image.jpg" alt="My Image" width="500" height="400">
  ```

#### Common `<img>` Attributes:

| Attribute    | Description                                                                                           | Example                                 |
|--------------|-------------------------------------------------------------------------------------------------------|-----------------------------------------|
| `src`        | Specifies the path to the image file, either relative or absolute.                                    | `src="images/photo.jpg"`                |
| `alt`        | Provides alternative text if the image fails to load, or for screen readers.                          | `alt="Picture of a sunset"`             |
| `width`      | Sets the width of the image (in pixels or percentages).                                               | `width="500"`                           |
| `height`     | Sets the height of the image (in pixels or percentages).                                              | `height="300"`                          |
| `title`      | Adds a tooltip that displays when hovering over the image.                                            | `title="Hover text"`                    |
| `loading`    | Determines if the image should be lazy-loaded (`lazy`) or loaded immediately (`eager`).               | `loading="lazy"`                        |

#### Example with All Attributes:
```html
<img src="images/photo.jpg" alt="A scenic mountain view" width="500" height="300" title="Mountain" loading="lazy">
```
---

### **2. Video**

HTML5 enables embedding video content directly into webpages without plugins.

#### Basic Video Embedding:
```html
<video controls>
  <source src="path/to/video.mp4" type="video/mp4">
  <source src="path/to/video.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>
```

#### Common `<video>` and `<source>` Attributes:

| Attribute  | Description                                                                            | Example                                     |
| ---------- | -------------------------------------------------------------------------------------- | ------------------------------------------- |
| `controls` | Displays playback controls like play, pause, and volume.                               | `<video controls>`                          |
| `autoplay` | Automatically plays the video on page load (not recommended due to user experience).   | `<video autoplay>`                          |
| `loop`     | Restarts the video automatically once it ends.                                         | `<video loop>`                              |
| `muted`    | Starts the video muted.                                                                | `<video muted>`                             |
| `poster`   | Specifies an image to show before the video loads or while it’s downloading.           | `<video poster="thumbnail.jpg">`            |
| `preload`  | Controls if/how the video should be preloaded. Options: `none`, `metadata`, or `auto`. | `<video preload="metadata">`                |
| `<source>` | Defines different video formats for browser compatibility (e.g., `.mp4`, `.ogg`).      | `<source src="video.mp4" type="video/mp4">` |

#### Example with Multiple Sources and Attributes:
```html
<video controls loop muted poster="thumbnail.jpg" preload="auto">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>
```


---

### **3. Embedding External Videos**
To embed external videos, like those from YouTube or other video platforms, HTML offers an easy way to do this using an `<iframe>`. This approach allows you to embed videos hosted on other sites directly into your webpage.

#### Basic Structure Using `<iframe>`
The `<iframe>` element is commonly used to embed YouTube, Vimeo, or other external video content into your webpage.

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

#### Common `<iframe>` Attributes for Videos:

| Attribute           | Description                                                                                                         | Example                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `src`               | URL of the video you want to embed. Replace `VIDEO_ID` with the actual video ID.                                   | `src="https://www.youtube.com/embed/dQw4w9WgXcQ"`   |
| `width`             | Sets the width of the iframe in pixels or percentages.                                                             | `width="560"`                                       |
| `height`            | Sets the height of the iframe in pixels or percentages.                                                            | `height="315"`                                      |
| `frameborder`       | Sets the width of the iframe’s border. A value of `0` removes the border.                                          | `frameborder="0"`                                   |
| `allow`             | Specifies features like autoplay, fullscreen, or camera access. Commonly used values include: `autoplay`, `encrypted-media`, `fullscreen`, and `picture-in-picture`. | `allow="autoplay; fullscreen"` |
| `allowfullscreen`   | Enables full-screen mode for the video, when available.                                                            | `allowfullscreen`                                   |
| `title`             | A descriptive title for accessibility and SEO purposes.                                                           | `title="My Video"`                                  |

#### Example Embedding a YouTube Video
```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="Example YouTube Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

*Replace `VIDEO_ID` with the unique identifier of the video (found in the YouTube URL).*

#### Example with Vimeo
```html
<iframe src="https://player.vimeo.com/video/VIDEO_ID" width="640" height="360" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen title="Example Vimeo Video"></iframe>
```

*Replace `VIDEO_ID` with the unique identifier for the Vimeo video.*

---

## **Section-2.6: Tables**

Tables are used to organize data in rows and columns, helping display information clearly.

#### Basic Table Structure:
```html
<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
</table>
```

#### Common Table Tags and Attributes:

| Tag              | Description                                                            | Example                                           |
|------------------|------------------------------------------------------------------------|---------------------------------------------------|
| `<table>`        | Wraps the entire table.                                               | `<table></table>`                                 |
| `<tr>`           | Defines a row in the table.                                           | `<tr><td>Row data</td></tr>`                      |
| `<th>`           | Creates a header cell, typically bold and centered.                   | `<th>Header</th>`                                 |
| `<td>`           | Creates a standard data cell in a table row.                          | `<td>Data</td>`                                   |
| `<caption>`      | Adds a title or caption to the table, usually above the table.        | `<caption>My Table</caption>`                     |
| `colspan`        | Sets the number of columns a cell should span.                        | `<td colspan="2">Spans 2 columns</td>`           |
| `rowspan`        | Sets the number of rows a cell should span.                           | `<td rowspan="3">Spans 3 rows</td>`              |
| `<thead>`        | Groups header rows, used with `<th>` elements.                        | `<thead><tr><th>Header</th></tr></thead>`         |
| `<tbody>`        | Groups the body content rows.                                         | `<tbody><tr><td>Data</td></tr></tbody>`           |
| `<tfoot>`        | Groups footer rows, typically for summary information.                | `<tfoot><tr><td>Footer Data</td></tr></tfoot>`    |


---

# **Section-3: Advanced HTML5 Elements**
### **Section-3.1: Forms**

#### `<form>`
- **Purpose**: Collects user input.
- **Attributes**:
  - `method`: Defines how data is sent (e.g., `GET` or `POST`).
  - `action`: URL to send form data.
#### **Example**: 

  ```html
  <form action="/submit" method="POST">
    <input type="text" name="username" required>
    <input type="submit" value="Submit">
  </form>
  ```

#### `<label>`
- **Purpose**: Associates text with a form input for better usability and accessibility. When the label is clicked, it focuses on the linked input field.
- **Attributes**:
  - **`for`**: Links the label to a specific input element by matching the `for` attribute's value with the input’s `id`.
  - **`class`**: Assigns a CSS class for styling purposes.
  - **`id`**: Provides a unique identifier for the label, useful in styling and scripting.
  - **`style`**: Adds inline CSS styling to the label.
  - **`title`**: Sets a tooltip that appears on hover, providing extra information.
  - **`hidden`**: Hides the label from view while still being accessible to screen readers.
  - **`aria-*`**: ARIA attributes (like `aria-label` or `aria-labelledby`) for enhanced accessibility, especially for screen readers.

- **Example**:
  ```html
  <form action="/submit" method="POST">
    <label for="username" class="form-label" style="color: blue;" title="Enter your username">
      Username:
    </label>
    <input type="text" id="username" name="username" required>
    
    <input type="submit" value="Submit">
  </form>
  ```

#### `<input>`
- **Purpose**: Provides various types of input fields.
- **Attributes**:
  - `type`: Defines input type (e.g., `text`, `submit`, `email`, `password`).
  - `required`: Marks field as mandatory.
  - `placeholder`: Shows a hint inside the field.
  - `min`, `max`: Set limits for numeric/date inputs.
  - `name`: Name used in form submission.

##### Common Input Types:

| Type       | Description                    |
| ---------- | ------------------------------ |
| `text`     | Single-line text input         |
| `submit`   | Submit button                  |
| `reset`    | Reset button                   |
| `email`    | Email input                    |
| `date`     | Date picker                    |
| `radio`    | Radio button (single choice)   |
| `password` | Password input (obscures text) |
##### Examples
1. **`text`** - A single-line text input field where the user can type text.
    
    ```html
    <input type="text" name="username" placeholder="Enter your username">
    ```
    
2. **`submit`** - A button that submits the form.
    
    ```html
    <input type="submit" value="Submit">
    ```
    
3. **`reset`** - A button that resets all the form fields to their initial values.
    
    ```html
    <input type="reset" value="Reset">
    ```
    
4. **`email`** - An input field specifically for entering email addresses, often with validation for proper email format.
    
    ```html
    <input type="email" name="email" placeholder="Enter your email">
    ```
    
5. **`date`** - A date picker that lets the user select a date.
    
    ```html
    <input type="date" name="birthdate">
    ```
    
6. **`radio`** - A set of radio buttons allowing the user to choose only one option.
    
    ```html
    <input type="radio" name="gender" value="male"> Male
    <input type="radio" name="gender" value="female"> Female
    ```
    
7. **`password`** - An input field that obscures the text typed by the user (used for passwords).
    
    ```html
    <input type="password" name="password" placeholder="Enter your password">
    ```
    

Let me know if this is what you were looking for!
The `<form>` tag has several attributes that control how the form behaves when it is submitted. Here’s a breakdown of the primary attributes, including a detailed explanation of `method` and the differences between `GET` and `POST`.

---

#### Attributes of the `<form>` Tag

3. **`action`**:
   - Specifies the URL where the form data will be sent when the user submits the form.
   - If this attribute is empty or omitted, the form data is sent to the same page where the form is displayed.
#### **Example**: 
`<form action="/submit-data">` sends the form data to `/submit-data`.

4. **`method`**:
   - Defines how the form data is sent to the server.
   - The two primary methods are `GET` and `POST`:
   
     - **`GET`**:
       - Appends form data to the URL in the form of a query string (e.g., `/submit?username=JohnDoe`).
       - Used for non-sensitive data, as the data is visible in the URL and limited by URL length restrictions.
       - Commonly used for search forms, filters, or other requests that don’t modify server data.
       - It’s generally faster and easier to bookmark or share, as the data is part of the URL.

     - **`POST`**:
       - Sends data in the body of the HTTP request, not visible in the URL.
       - Commonly used for sensitive data (e.g., passwords) and for actions that modify server data, such as creating accounts or submitting contact forms.
       - Has no length limitations, making it suitable for larger submissions.
       - Provides better security for sensitive data compared to `GET`.

   - Example:
     ```html
     <form action="/submit-data" method="POST">
     ```
   **Summary of GET vs. POST**:

5. **`enctype`** (Encoding Type):
   - Defines how the form data should be encoded when submitting to the server.
   - Common values:
     - **`application/x-www-form-urlencoded`** (default): Encodes data as URL-encoded key-value pairs.
     - **`multipart/form-data`**: Used for file uploads, allowing binary data like images or PDFs.
     - **`text/plain`**: Sends data as plain text, mainly for testing purposes.
#### **Example**: 
`<form enctype="multipart/form-data">` is necessary for file uploads.

6. **`target`**:
   - Specifies where to display the response after form submission.
   - Common values:
     - **`_self`** (default): Opens the response in the same tab.
     - **`_blank`**: Opens the response in a new tab.
     - **`_parent`**: Loads the response in the parent frame, if nested in an iframe.
     - **`_top`**: Opens the response in the topmost frame (useful in multi-frame situations).
#### **Example**: 
`<form target="_blank">` opens the form response in a new tab.

7. **`autocomplete`**:
   - Allows browsers to automatically fill in previously entered data for known fields (like usernames, addresses).
   - Values:
     - **`on`** (default): Enables auto-complete.
     - **`off`**: Disables auto-complete.
#### **Example**: 
`<form autocomplete="off">` prevents browsers from auto-filling form fields.

8. **`novalidate`**:
   - Disables HTML5 validation for the form, allowing submission without checking for validity (e.g., `required` fields or `pattern` checks).
   - Use this for cases where validation is handled solely by JavaScript or server-side validation.
#### **Example**: 
`<form novalidate>` bypasses HTML5 validation rules.

---

#### Example of a Form Using Multiple Attributes
Here’s a form that incorporates these attributes:

```html
<form action="/submit-data" method="POST" enctype="multipart/form-data" target="_blank" autocomplete="off">
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required>
    
    <label for="fileUpload">Upload File:</label>
    <input type="file" id="fileUpload" name="fileUpload">
    
    <input type="submit" value="Submit">
</form>
```

In this example:
- **Data** is submitted to `/submit-data`.
- **`method="POST"`** hides the data in the body, making it more secure.
- **`enctype="multipart/form-data"`** allows for file uploads.
- **`target="_blank"`** opens the submission result in a new tab.
- **`autocomplete="off"`** disables browser auto-fill suggestions.

---

### **Section-3.2: Dropdown**

#### `<select>` and `<option>`
- **Purpose**: Creates a dropdown menu.
- **Example**: 
  ```html
  <select name="options">
    <option value="1">Option 1</option>
    <option value="2">Option 2</option>
  </select>
  ```

---

### **Section-3.3: Comments**

#### `<!-- -->`
- **Purpose**: Adds comments that won’t appear on the webpage.
- **Example**: 
  ```html
  <!-- This is a comment -->
  ```

### **Section-3.4: Collective Character Objects**

This section appears to focus on special characters or symbols used in HTML and possibly other markup languages. I'll continue from where you left off, expanding on some of the characters and their usage:

#### `&#34;` & `&quot;` - Quotation Marks

- **Purpose**: Both `&#34;` (numeric character reference) and `&quot;` (named character reference) represent double quotation marks (`"`). These are useful when you need to include quotation marks in attributes or text without breaking the HTML syntax.
    
    **Example**:
    
    ```html
    <p>This is a "quoted" text.</p>
    <!-- Alternatively -->
    <p>This is a &quot;quoted&quot; text.</p>
    ```
    

#### `&#39;` & `&apos;` - Apostrophe/Single Quote

- **Purpose**: `&#39;` (numeric character reference) and `&apos;` (named character reference) represent a single quotation mark or apostrophe (`'`). This is particularly useful in cases where you need to avoid confusion with HTML attribute delimiters.
    
    **Example**:
    
    ```html
    <p>It&#39;s a beautiful day.</p>
    <!-- Alternatively -->
    <p>It&apos;s a beautiful day.</p>
    ```
    

#### `&#38;` & `&amp;` - Ampersand (`&`)

- **Purpose**: Both `&#38;` (numeric) and `&amp;` (named) represent the ampersand (`&`) symbol. This is critical to use in HTML when the ampersand is part of text, as it is also used in character references and could interfere with parsing.
    
    **Example**:
    
    ```html
    <p>Tom &amp; Jerry</p>
    <!-- Alternatively -->
    <p>Tom &#38; Jerry</p>
    ```
    

#### `&#60;` & `&lt;` - Less Than (`<`)

- **Purpose**: Both `&#60;` and `&lt;` represent the less-than sign (`<`). Since the `<` character is used for opening tags in HTML, using these entities is necessary when you need to display the symbol as part of the content.
    
    **Example**:
    
    ```html
    <p>5 &lt; 10</p>
    ```
    

#### `&#62;` & `&gt;` - Greater Than (`>`)

- **Purpose**: `&#62;` and `&gt;` represent the greater-than sign (`>`). Similar to the less-than sign, the greater-than sign is used for closing tags in HTML, so you need these entities for displaying it within content.
    
    **Example**:
    
    ```html
    <p>10 &gt; 5</p>
    ```
    

#### `&#160;` & `&nbsp;` - Non-breaking Space

- **Purpose**: Both `&#160;` (numeric) and `&nbsp;` (named) represent a non-breaking space, which is used to prevent line breaks where a space would normally occur (such as between words or in numbers).
    
    **Example**:
    
    ```html
    <p>My&nbsp;name&nbsp;is&nbsp;John.</p>
    ```
    

#### `&#169;` & `&copy;` - Copyright Symbol

- **Purpose**: Both `&#169;` and `&copy;` represent the copyright symbol (`©`). These entities are important when displaying legal symbols or text content in HTML.
    
    **Example**:
    
    ```html
    <p>&copy; 2025 My Company. All rights reserved.</p>
    ```
    

#### `&#174;` & `&reg;` - Registered Trademark Symbol

- **Purpose**: Both `&#174;` and `&reg;` represent the registered trademark symbol (`®`), which is used to indicate a legally registered trademark.
    
    **Example**:
    
    ```html
    <p>MyProduct&reg; is a registered trademark.</p>
    ```
    

#### `&#8482;` & `&trade;` - Trademark Symbol

- **Purpose**: Both `&#8482;` and `&trade;` represent the trademark symbol (`™`), used to denote a trademark or brand that is not yet registered.
    
    **Example**:
    
    ```html
    <p>MyBrand&trade; is a trademark of MyCompany.</p>
    ```
    

---

These are just a few common collective character objects used in HTML. Using these character references allows for the safe inclusion of symbols that could otherwise interfere with HTML syntax or markup, ensuring that your page displays the characters correctly.


---
---

## **Reference Websites**

| Website                         | Link                                      |
|----------------------------------|-------------------------------------------|
| **W3Schools**                    | [W3Schools](https://www.w3schools.com/)   |
| **MDN Web Docs**                 | [MDN Web Docs](https://developer.mozilla.org/) |
| **StackOverflow**                | [StackOverflow](https://stackoverflow.com/) |
Here is an expanded set of notes for HTML5 using the same format, optimized for Obsidian. 

---

# Section 4: HTML5 Additional Concepts and Elements for Full-Stack Development

### HTML5 APIs
Modern HTML5 provides several built-in APIs that enable adding advanced features to websites.

#### Key APIs:
| API                 | Description                                                                   | Example Use                 |
| ------------------- | ----------------------------------------------------------------------------- | --------------------------- |
| **Geolocation API** | Allows access to the user’s location (with permission).                       | Getting location info       |
| **Web Storage API** | Provides `localStorage` and `sessionStorage` for storing data in the browser. | Saving user data locally    |
| **Canvas API**      | Enables drawing and animations on the page.                                   | Creating graphics or charts |
| **Audio/Video API** | Embeds audio and video elements with playback control.                        | Integrating multimedia      |
| **Drag and Drop**   | Enables drag-and-drop functionality within the browser.                       | Rearranging list items      |

---
