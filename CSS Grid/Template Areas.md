# Template Areas in CSS Grid

**Description**: The `grid-template-areas` property in CSS Grid Layout allows you to create named areas within a grid container. These areas simplify the process of placing and arranging grid items, making the layout more readable and maintainable.

### How It Works

- The grid container is divided into named regions or "template areas" using the `grid-template-areas` property.
- Each grid item is assigned to a specific area by setting the `grid-area` property on that item.
- The names of these areas are written within strings in the `grid-template-areas` property to visually represent the layout.

### Syntax

```css
.container {
    display: grid;
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
}
```

In this example, the grid is divided into three rows:
- The first row is designated for the "header" area.
- The second row has "sidebar" on the left and "main" taking up the rest of the row.
- The third row is a single "footer" area.

### Defining Grid Areas

1. **`grid-template-areas`**: Defines the layout structure by assigning names to different sections of the grid. Each string represents a row in the grid, and each named area represents a cell or group of cells.

   - **Example**:
     ```css
     .container {
         display: grid;
         grid-template-columns: 1fr 2fr 1fr; /* Defines column widths */
         grid-template-rows: auto 1fr auto;  /* Defines row heights */
         grid-template-areas:
             "header header header"
             "sidebar main main"
             "footer footer footer";
     }
     ```

2. **`grid-area`**: Assigns a specific grid item to a defined area within `grid-template-areas`.

   - **Example**:
     ```css
     .header {
         grid-area: header;
     }
     .sidebar {
         grid-area: sidebar;
     }
     .main {
         grid-area: main;
     }
     .footer {
         grid-area: footer;
     }
     ```

### Full Example of Template Areas

Here's an example of HTML and CSS using template areas for a typical web page layout:

**HTML**:
```html
<div class="container">
    <header class="header">Header</header>
    <aside class="sidebar">Sidebar</aside>
    <main class="main">Main Content</main>
    <footer class="footer">Footer</footer>
</div>
```

**CSS**:
```css
.container {
    display: grid;
    grid-template-columns: 1fr 3fr 1fr;   /* Define column widths */
    grid-template-rows: auto 1fr auto;    /* Define row heights */
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
    gap: 10px; /* Adds space between grid items */
}

.header {
    grid-area: header;
    background-color: lightblue;
}

.sidebar {
    grid-area: sidebar;
    background-color: lightcoral;
}

.main {
    grid-area: main;
    background-color: lightgreen;
}

.footer {
    grid-area: footer;
    background-color: lightgoldenrodyellow;
}
```

### Important Properties in Template Areas

- **`grid-template-rows` and `grid-template-columns`**: Define the sizes of rows and columns respectively.
  - **Example**:
    ```css
    grid-template-rows: 100px auto 50px;
    grid-template-columns: 200px auto;
    ```

- **`gap`**: Adds spacing between grid items, which can be defined as `gap`, `row-gap`, and `column-gap`.
  - **Example**:
    ```css
    gap: 20px; /* Space between all items */
    ```

### Benefits of Using Template Areas

1. **Readability**: Using names for grid areas makes the code more readable and descriptive.
2. **Easier Layout Management**: Changing layout structures becomes easier, as you can rearrange elements simply by modifying the template areas.
3. **Responsive Design**: Template areas can adapt to different screen sizes, which is especially useful when combined with media queries.

### Responsive Layouts with Template Areas

You can use media queries to adjust the `grid-template-areas` for different screen sizes. For example:

```css
@media (max-width: 600px) {
    .container {
        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "footer";
        grid-template-columns: 1fr;
    }
}
```

In this media query:
- The grid layout changes to a single-column layout for small screens, stacking the `header`, `main`, `sidebar`, and `footer` areas vertically.

### Summary

Template areas in CSS Grid offer a flexible and intuitive way to design complex layouts. By using descriptive area names and aligning grid items within defined regions, you can create responsive, organized, and easy-to-read layouts.
