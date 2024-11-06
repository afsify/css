# Grid Container Properties

The CSS Grid Layout module enables the creation of complex, two-dimensional grid-based layouts. Grid container properties are used on the parent container to define the structure and behavior of the grid.

### Setting Up a Grid Container

To make an element a grid container, set its `display` property to `grid` or `inline-grid`:

```css
.container {
    display: grid; /* or inline-grid for inline behavior */
}
```

### Key Grid Container Properties

#### 1. `grid-template-columns` and `grid-template-rows`

- **Description**: Defines the number and size of columns and rows in the grid.
- **Values**: Any length, percentage, or flexible units (`fr`, `px`, `%`, `em`, etc.).
  - `fr` (fractional unit): Distributes available space proportionally.
  - Fixed units: `px`, `em`, `%`, `rem`, etc.
  - `repeat()`: Allows repeating a specified number of columns or rows.
  - `auto`: Automatically sizes based on content.
- **Example**:
    ```css
    .container {
        display: grid;
        grid-template-columns: 1fr 2fr; /* Two columns: 1/3 and 2/3 */
        grid-template-rows: 100px 200px; /* Two rows: 100px and 200px */
    }

    /* Using repeat and flexible units */
    .container {
        grid-template-columns: repeat(3, 1fr); /* Three equal-width columns */
        grid-template-rows: repeat(2, 150px); /* Two rows of 150px */
    }
    ```

#### 2. `grid-template-areas`

- **Description**: Defines named areas within the grid. Useful for positioning items by their names instead of line numbers.
- **Syntax**: Use strings to represent grid areas, with each string representing a row. Named areas can be placed by referencing `grid-area` in child elements.
- **Example**:
    ```css
    .container {
        display: grid;
        grid-template-columns: 1fr 2fr;
        grid-template-rows: auto auto;
        grid-template-areas: 
            "header header"
            "sidebar content"
            "footer footer";
    }

    .header { grid-area: header; }
    .sidebar { grid-area: sidebar; }
    .content { grid-area: content; }
    .footer { grid-area: footer; }
    ```

#### 3. `gap` (or `grid-gap`)

- **Description**: Sets the spacing between grid rows and columns. This property can be split into `row-gap` and `column-gap`.
- **Values**: Any length unit (`px`, `em`, `%`, etc.).
- **Example**:
    ```css
    .container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px; /* Adds 20px gap between rows and columns */
    }
    ```

#### 4. `justify-items`

- **Description**: Aligns grid items along the inline (horizontal) axis within their cells.
- **Values**:
  - `start`: Aligns items to the start of the cell.
  - `end`: Aligns items to the end of the cell.
  - `center`: Centers items in the cell.
  - `stretch` (default): Stretches items to fill the cell.
- **Example**:
    ```css
    .container {
        display: grid;
        justify-items: center; /* Centers items horizontally in each cell */
    }
    ```

#### 5. `align-items`

- **Description**: Aligns grid items along the block (vertical) axis within their cells.
- **Values**: Same as `justify-items` (`start`, `end`, `center`, `stretch`).
- **Example**:
    ```css
    .container {
        display: grid;
        align-items: start; /* Aligns items to the top of each cell */
    }
    ```

#### 6. `justify-content`

- **Description**: Aligns the entire grid within the container along the inline (horizontal) axis.
- **Values**:
  - `start`: Aligns grid to the start of the container.
  - `end`: Aligns grid to the end of the container.
  - `center`: Centers the grid within the container.
  - `space-between`, `space-around`, `space-evenly`: Distributes space around the grid tracks.
- **Example**:
    ```css
    .container {
        display: grid;
        justify-content: space-around; /* Adds space around the entire grid */
    }
    ```

#### 7. `align-content`

- **Description**: Aligns the entire grid along the block (vertical) axis.
- **Values**: Similar to `justify-content` (`start`, `end`, `center`, `space-between`, `space-around`, `space-evenly`).
- **Example**:
    ```css
    .container {
        display: grid;
        align-content: center; /* Centers grid vertically within the container */
    }
    ```

#### 8. `grid-auto-rows` and `grid-auto-columns`

- **Description**: Defines the size of implicitly created rows or columns, for cases where items exceed the defined grid structure.
- **Values**: Any length unit (`px`, `fr`, `%`, `auto`).
- **Example**:
    ```css
    .container {
        display: grid;
        grid-template-columns: 1fr 2fr;
        grid-auto-rows: 100px; /* New rows will have a height of 100px */
    }
    ```

#### 9. `grid-auto-flow`

- **Description**: Controls the automatic placement of items that do not have an explicit grid position.
- **Values**:
  - `row` (default): Fills rows first, then moves to the next row.
  - `column`: Fills columns first, then moves to the next column.
  - `dense`: Fills in gaps in the grid layout, trying to utilize space efficiently.
- **Example**:
    ```css
    .container {
        display: grid;
        grid-auto-flow: dense; /* Fills gaps for a more compact layout */
    }
    ```

### Practical Example of Grid Container Properties

```html
<div class="container">
    <div class="item item1">Item 1</div>
    <div class="item item2">Item 2</div>
    <div class="item item3">Item 3</div>
    <div class="item item4">Item 4</div>
</div>
```

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* Two equal-width columns */
    grid-template-rows: auto;
    gap: 15px; /* Space between items */
    justify-content: center; /* Center grid horizontally */
    align-content: start; /* Align grid to the top */
}

.item {
    padding: 20px;
    background-color: lightblue;
    text-align: center;
}
```

### Best Practices

- **Use `fr` Units**: The `fr` unit is highly flexible and adapts well to different screen sizes, making it ideal for responsive designs.
- **Combine `grid-template-areas` with Named Items**: Using `grid-template-areas` helps make layouts more readable and maintainable.
- **Leverage Implicit Grid for Extra Items**: Define `grid-auto-rows` and `grid-auto-columns` for cases where items exceed the initial structure, allowing for more adaptive designs.
- **Experiment with `justify-content` and `align-content`**: These properties control grid placement within the container and can be useful for centering or spacing grids efficiently.

### Summary

CSS Grid Container properties allow you to create powerful and adaptable grid layouts with precise control over columns, rows, spacing, and alignment. Mastering these properties enables the creation of responsive, well-organized layouts that work across various screen sizes and devices.
