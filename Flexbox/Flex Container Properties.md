# Flexbox: Flex Container Properties

Flexbox (Flexible Box Layout) is a CSS layout model that allows for the easy arrangement of elements in a flexible and responsive manner. It provides powerful alignment and distribution capabilities for layout design. The container that holds flex items is known as the **flex container**, and it has several properties that control the layout of its children.

---

### 1. **Display Property**

- **`display: flex;`**
  - Establishes a flex container and enables flexbox layout.
  - Example:
    ```css
    .flex-container {
      display: flex;
    }
    ```

- **`display: inline-flex;`**
  - Similar to `flex`, but the container behaves like an inline element.
  - Example:
    ```css
    .inline-flex-container {
      display: inline-flex;
    }
    ```

---

### 2. **Flex Direction**

- **`flex-direction`**
  - Defines the direction flex items are placed in the flex container.
  - Values:
    - `row` (default): Items are arranged from left to right.
    - `row-reverse`: Items are arranged from right to left.
    - `column`: Items are arranged from top to bottom.
    - `column-reverse`: Items are arranged from bottom to top.
  - Example:
    ```css
    .flex-container {
      flex-direction: column;
    }
    ```

---

### 3. **Flex Wrap**

- **`flex-wrap`**
  - Controls whether flex items should wrap onto multiple lines or stay on one line.
  - Values:
    - `nowrap` (default): All items will be on one line.
    - `wrap`: Items will wrap onto multiple lines, from top to bottom.
    - `wrap-reverse`: Items will wrap onto multiple lines, from bottom to top.
  - Example:
    ```css
    .flex-container {
      flex-wrap: wrap;
    }
    ```

---

### 4. **Flex Flow**

- **`flex-flow`**
  - A shorthand property for `flex-direction` and `flex-wrap`.
  - Example:
    ```css
    .flex-container {
      flex-flow: row wrap;
    }
    ```

---

### 5. **Justify Content**

- **`justify-content`**
  - Aligns flex items along the main axis (horizontal if `flex-direction` is `row`).
  - Values:
    - `flex-start`: Items are packed toward the start of the flex container.
    - `flex-end`: Items are packed toward the end of the flex container.
    - `center`: Items are centered along the main axis.
    - `space-between`: Items are distributed evenly, with the first item at the start and the last at the end.
    - `space-around`: Items are distributed evenly with space around them.
    - `space-evenly`: Items are distributed with equal space between them.
  - Example:
    ```css
    .flex-container {
      justify-content: space-between;
    }
    ```

---

### 6. **Align Items**

- **`align-items`**
  - Aligns flex items along the cross axis (vertical if `flex-direction` is `row`).
  - Values:
    - `stretch` (default): Items stretch to fill the container.
    - `flex-start`: Items are aligned at the start of the cross axis.
    - `flex-end`: Items are aligned at the end of the cross axis.
    - `center`: Items are centered along the cross axis.
    - `baseline`: Items are aligned along their baseline.
  - Example:
    ```css
    .flex-container {
      align-items: center;
    }
    ```

---

### 7. **Align Content**

- **`align-content`**
  - Aligns flex lines (if the flex container has multiple lines) along the cross axis.
  - Values:
    - `flex-start`: Lines are packed to the start of the container.
    - `flex-end`: Lines are packed to the end of the container.
    - `center`: Lines are centered.
    - `space-between`: Lines are distributed evenly with space between them.
    - `space-around`: Lines are distributed with space around them.
    - `stretch`: Lines stretch to fill the container.
  - Example:
    ```css
    .flex-container {
      align-content: space-around;
    }
    ```

---

### 8. **Gap**

- **`gap`**
  - Specifies the space between flex items (replaces `margin` on items for better control).
  - Example:
    ```css
    .flex-container {
      gap: 10px;
    }
    ```

---

### Summary

The properties of the flex container allow for extensive control over the layout and alignment of flex items. By utilizing these properties effectively, developers can create dynamic and responsive designs that adapt to various screen sizes and orientations. Flexbox is particularly useful for building complex layouts without the need for floats or positioning hacks.