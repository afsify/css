# CSS Selectors

Selectors in CSS are used to select HTML elements to apply styles. They are essential for targeting specific elements based on attributes, classes, IDs, relationships, and more. Here's an in-depth look at CSS selectors, their types, and usage with examples.

---

### 1. **Basic Selectors**

1. **Universal Selector (`*`)**
   - Selects all elements on the page.
   - Syntax: `* { /* Styles */ }`
   - Example:
     ```css
     * {
       margin: 0;
       padding: 0;
     }
     ```

2. **Type Selector**
   - Selects all elements of a given type (tag name).
   - Syntax: `tagname { /* Styles */ }`
   - Example:
     ```css
     p {
       color: blue;
     }
     ```

3. **Class Selector (`.`)**
   - Targets elements with a specific class attribute.
   - Syntax: `.classname { /* Styles */ }`
   - Example:
     ```css
     .highlight {
       background-color: yellow;
     }
     ```

4. **ID Selector (`#`)**
   - Selects an element by its unique `id`.
   - Syntax: `#idname { /* Styles */ }`
   - Example:
     ```css
     #main-header {
       font-size: 2rem;
     }
     ```

5. **Attribute Selector**
   - Targets elements based on attribute values.
   - Syntax: `[attribute=value] { /* Styles */ }`
   - Example:
     ```css
     input[type="text"] {
       border: 1px solid gray;
     }
     ```

---

### 2. **Combinator Selectors**

1. **Descendant Selector (space)**
   - Selects all elements that are descendants of a specified element.
   - Syntax: `parent child { /* Styles */ }`
   - Example:
     ```css
     div p {
       color: green;
     }
     ```

2. **Child Selector (`>`)**
   - Selects elements that are direct children of a specified element.
   - Syntax: `parent > child { /* Styles */ }`
   - Example:
     ```css
     ul > li {
       list-style-type: none;
     }
     ```

3. **Adjacent Sibling Selector (`+`)**
   - Selects the element immediately following another element.
   - Syntax: `element1 + element2 { /* Styles */ }`
   - Example:
     ```css
     h1 + p {
       margin-top: 0;
     }
     ```

4. **General Sibling Selector (`~`)**
   - Selects all siblings after a specified element.
   - Syntax: `element1 ~ element2 { /* Styles */ }`
   - Example:
     ```css
     h1 ~ p {
       color: darkgray;
     }
     ```

---

### 3. **Pseudo-Classes**

1. **`:hover`**
   - Applied when the user hovers over an element.
   - Example:
     ```css
     button:hover {
       background-color: blue;
     }
     ```

2. **`:nth-child()`**
   - Selects elements based on their position within a parent.
   - Example:
     ```css
     li:nth-child(odd) {
       background-color: #f2f2f2;
     }
     ```

3. **`:first-child` and `:last-child`**
   - `:first-child` targets the first child of a parent; `:last-child` targets the last.
   - Example:
     ```css
     p:first-child {
       font-weight: bold;
     }
     ```

---

### 4. **Pseudo-Elements**

1. **`::before` and `::after`**
   - Inserts content before or after an element’s actual content.
   - Example:
     ```css
     h2::before {
       content: "★ ";
       color: gold;
     }
     ```

2. **`::first-line` and `::first-letter`**
   - Targets the first line or first letter of an element.
   - Example:
     ```css
     p::first-line {
       font-weight: bold;
     }
     ```

---

### 5. **Attribute Selectors in Depth**

1. **[attribute] Selector**
   - Selects elements with a specific attribute.
   - Example:
     ```css
     [disabled] {
       opacity: 0.5;
     }
     ```

2. **[attribute^="value"]**
   - Selects elements with an attribute that starts with a specified value.
   - Example:
     ```css
     a[href^="https"] {
       color: blue;
     }
     ```

3. **[attribute$="value"]**
   - Selects elements with an attribute that ends with a specified value.
   - Example:
     ```css
     img[src$=".png"] {
       border: 1px solid black;
     }
     ```

4. **[attribute*="value"]**
   - Selects elements with an attribute that contains a specified value.
   - Example:
     ```css
     a[href*="example"] {
       color: green;
     }
     ```

---

### Practical Examples

1. **Navigation Styling**
   ```css
   nav ul li a:hover {
     color: red;
     text-decoration: underline;
   }
   ```

2. **Styling a Form**
   ```css
   input[type="text"] {
     padding: 8px;
     border: 1px solid #ccc;
   }

   input[type="submit"]:hover {
     background-color: green;
     color: white;
   }
   ```

3. **Using `nth-child` for Table Rows**
   ```css
   table tr:nth-child(even) {
     background-color: #f9f9f9;
   }
   ```

---

### Summary

CSS Selectors form the foundation of targeting and styling HTML elements effectively. By understanding and combining various selectors, developers can apply styles precisely and efficiently, allowing for rich, responsive, and interactive designs.