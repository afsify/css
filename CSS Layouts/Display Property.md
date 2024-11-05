# CSS Layouts

CSS layouts define how elements are arranged on a page, enabling responsive, structured, and visually appealing designs. They provide control over the positioning and alignment of elements, allowing developers to create both simple and complex layouts.

#### Key Layout Techniques in CSS:

1. **Normal Flow**
   - **Inline Elements**: Flow horizontally (e.g., `<span>`, `<a>`)
   - **Block Elements**: Stack vertically, taking full width (e.g., `<div>`, `<p>`)

2. **Flexbox Layout**
   - A one-dimensional layout system ideal for laying out items in rows or columns.
   - Properties:
     - **`display: flex`**: Enables Flexbox on a container.
     - **`flex-direction`**: Defines the direction of items (row, column).
     - **`justify-content`**: Aligns items horizontally (start, center, space-between).
     - **`align-items`**: Aligns items vertically in the container (flex-start, center).
   - Example:
     ```css
     .flex-container {
       display: flex;
       flex-direction: row;
       justify-content: space-between;
       align-items: center;
     }
     ```

3. **Grid Layout**
   - A two-dimensional system for creating both rows and columns.
   - Properties:
     - **`display: grid`**: Enables Grid on a container.
     - **`grid-template-columns` / `grid-template-rows`**: Defines the size and number of columns/rows.
     - **`grid-gap`**: Adds space between grid items.
     - **`grid-area`**: Assigns grid areas to items.
   - Example:
     ```css
     .grid-container {
       display: grid;
       grid-template-columns: repeat(3, 1fr);
       grid-gap: 10px;
     }
     ```

4. **Positioning**
   - **Static**: Default flow positioning.
   - **Relative**: Positioned relative to itself.
   - **Absolute**: Positioned relative to the nearest positioned ancestor.
   - **Fixed**: Fixed to the viewport.
   - **Sticky**: Switches between relative and fixed, depending on scroll position.
   - Example:
     ```css
     .absolute-box {
       position: absolute;
       top: 10px;
       left: 20px;
     }
     ```

5. **CSS Columns**
   - Enables multi-column layouts, similar to newspaper columns.
   - Properties:
     - **`column-count`**: Sets the number of columns.
     - **`column-gap`**: Sets the gap between columns.
   - Example:
     ```css
     .column-container {
       column-count: 3;
       column-gap: 15px;
     }
     ```

6. **CSS Table Layout**
   - Uses `display: table`, `display: table-row`, and `display: table-cell` to create a table-like layout for complex arrangements.

---

### Display Property

The `display` property is fundamental in controlling how elements appear and interact in layouts. It defines the type of rendering box used for an element.

#### Display Property Values:

1. **`display: block`**
   - Element starts on a new line and takes up the full width available.
   - Commonly used for layout structuring.
   - Example:
     ```css
     .block-element {
       display: block;
     }
     ```

2. **`display: inline`**
   - Element does not start on a new line and only takes up as much width as necessary.
   - Suitable for text elements and inline content.
   - Example:
     ```css
     .inline-element {
       display: inline;
     }
     ```

3. **`display: inline-block`**
   - Combines `inline` flow with `block` features, such as padding and margin.
   - Useful for buttons and small layout sections.
   - Example:
     ```css
     .inline-block-element {
       display: inline-block;
       padding: 10px;
       margin: 5px;
     }
     ```

4. **`display: flex`**
   - Turns an element into a flexible container with Flexbox properties.
   - Provides extensive control over child element alignment and spacing.
   - Example:
     ```css
     .flex-container {
       display: flex;
       justify-content: space-around;
     }
     ```

5. **`display: grid`**
   - Creates a grid container for organizing elements in rows and columns.
   - Suitable for complex layouts with overlapping elements.
   - Example:
     ```css
     .grid-container {
       display: grid;
       grid-template-columns: auto auto;
       grid-gap: 20px;
     }
     ```

6. **`display: table`**
   - Makes an element behave like a `<table>`, with children acting like rows or cells.
   - Useful for layout consistency without traditional table HTML.
   - Example:
     ```css
     .table-container {
       display: table;
     }
     ```

7. **`display: none`**
   - Removes the element from the document flow, making it invisible and inaccessible.
   - Common for hiding elements.
   - Example:
     ```css
     .hidden-element {
       display: none;
     }
     ```

8. **Other Values:**
   - **`display: contents`**: Makes the element disappear visually, but its children remain.
   - **`display: list-item`**: Adds a list-item marker (for lists).
   - **`display: inherit`**: Inherits the display value from its parent.

---

### Example: Display Property with Layouts

Here’s an example of combining display values to structure a simple webpage:

```html
<div class="container">
  <header class="header">Header</header>
  <nav class="nav">Navigation</nav>
  <main class="content">Main Content</main>
  <footer class="footer">Footer</footer>
</div>
```

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "nav content"
    "footer footer";
  grid-gap: 10px;
}

.header {
  grid-area: header;
  display: block;
}

.nav {
  grid-area: nav;
  display: inline-block;
  width: 150px;
}

.content {
  grid-area: content;
  display: block;
}

.footer {
  grid-area: footer;
  display: flex;
  justify-content: center;
}
```

In this layout:
- **Header** and **Content** use `display: block` for full-width layout.
- **Navigation** uses `inline-block` for a sidebar effect.
- **Footer** uses `flex` for centered alignment within the grid area.

--- 

These notes outline core layout techniques and the versatile `display` property, helping developers craft organized, responsive, and visually coherent designs.