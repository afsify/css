# CSS Pseudo-classes

A **pseudo-class** is a keyword added to selectors that specifies a special state of the selected elements. Pseudo-classes are preceded by a colon (`:`) and can target elements based on user interaction, element position, or other conditions.

### General Syntax
```css
selector:pseudo-class {
    /* styles */
}
```

### Commonly Used Pseudo-classes

#### 1. **:hover**
- **Description**: Targets an element when the user hovers over it with the mouse.
- **Usage**: Commonly used for interactive elements like buttons, links, or images.
  
  ```css
  a:hover {
      color: red;  /* Changes text color to red when hovering over a link */
  }
  ```

#### 2. **:focus**
- **Description**: Applies styles to an element when it gains focus, such as when a user clicks on a form input or navigates to it using the keyboard.
- **Usage**: Often used to highlight active form fields or interactive elements.
  
  ```css
  input:focus {
      border-color: blue;  /* Changes the border color of input when it is focused */
  }
  ```

#### 3. **:active**
- **Description**: Applies styles to an element while it is being activated (e.g., when a user clicks on a link or button).
- **Usage**: Typically used to style links or buttons during the "click" phase.
  
  ```css
  button:active {
      background-color: grey;  /* Changes the background when the button is pressed */
  }
  ```

#### 4. **:first-child**
- **Description**: Targets the first child element of a parent.
- **Usage**: Useful for styling the first element in a list or other container.
  
  ```css
  p:first-child {
      font-weight: bold;  /* Makes the first paragraph child bold */
  }
  ```

#### 5. **:last-child**
- **Description**: Targets the last child element of a parent.
- **Usage**: Useful for removing or adding styles to the last element in a container, such as removing the margin after the last item in a list.
  
  ```css
  ul li:last-child {
      margin-bottom: 0;  /* Removes the bottom margin from the last list item */
  }
  ```

#### 6. **:nth-child()**
- **Description**: Targets elements based on their position in a parent element, with a variety of ways to specify which elements to select.
- **Usage**: You can select elements using various patterns such as even, odd, or a specific number.
  
  ```css
  li:nth-child(2) {
      color: green;  /* Targets the second list item */
  }

  li:nth-child(even) {
      background-color: lightgrey;  /* Targets all even-numbered list items */
  }

  li:nth-child(3n) {
      font-size: 18px;  /* Targets every third list item */
  }
  ```

#### 7. **:nth-of-type()**
- **Description**: Similar to `:nth-child()`, but it targets elements of a specific type (e.g., all paragraphs, divs) rather than just any element.
- **Usage**: Useful when you want to target elements of a certain type in a parent.

  ```css
  p:nth-of-type(odd) {
      color: blue;  /* Targets odd-numbered paragraphs in a container */
  }
  ```

#### 8. **:not()**
- **Description**: Selects every element that does not match the given selector inside the `:not()` function.
- **Usage**: Helpful for excluding specific elements from a group.
  
  ```css
  div:not(.highlight) {
      background-color: lightgrey;  /* Applies a background color to all divs except those with class 'highlight' */
  }
  ```

#### 9. **:checked**
- **Description**: Targets elements that are checked, such as checkboxes or radio buttons.
- **Usage**: Used for styling form elements that are checked, useful in forms and interactive UIs.
  
  ```css
  input:checked {
      background-color: green;  /* Changes the background color of a checked checkbox */
  }
  ```

#### 10. **:disabled**
- **Description**: Selects disabled form elements like buttons, inputs, and select elements.
- **Usage**: Useful for styling disabled form fields or buttons.
  
  ```css
  input:disabled {
      background-color: lightgray;  /* Applies a light gray background to disabled input elements */
  }
  ```

#### 11. **:enabled**
- **Description**: Targets form elements that are enabled.
- **Usage**: Useful for styling form elements that are available for interaction.
  
  ```css
  button:enabled {
      cursor: pointer;  /* Changes the cursor to a pointer when the button is enabled */
  }
  ```

#### 12. **:empty**
- **Description**: Targets elements that have no children, including text nodes.
- **Usage**: Useful for styling empty elements, such as empty paragraphs or divs.
  
  ```css
  div:empty {
      background-color: lightblue;  /* Applies a background color to empty div elements */
  }
  ```

#### 13. **:root**
- **Description**: Targets the highest-level parent element (typically `<html>`), and it’s often used in custom properties (CSS variables).
- **Usage**: Commonly used for defining global variables.
  
  ```css
  :root {
      --main-color: #3498db;  /* Sets a CSS variable */
  }
  ```

#### 14. **:before and :after**
- **Description**: The `:before` pseudo-class allows you to insert content before an element, and `:after` inserts content after an element.
- **Usage**: Often used for adding decorative content like icons, labels, or styling purposes.
  
  ```css
  p:before {
      content: "→ ";  /* Adds a right arrow before each paragraph */
  }

  p:after {
      content: " ←";  /* Adds a left arrow after each paragraph */
  }
  ```

---

### Advanced Pseudo-classes

#### 1. **:first-of-type**
- **Description**: Selects the first element of its type (e.g., the first `<p>` in a container of different elements).
  
  ```css
  p:first-of-type {
      font-weight: bold;  /* Makes the first paragraph bold */
  }
  ```

#### 2. **:last-of-type**
- **Description**: Selects the last element of its type (e.g., the last `<p>` in a container).
  
  ```css
  p:last-of-type {
      color: red;  /* Changes the color of the last paragraph */
  }
  ```

#### 3. **:root**
- **Description**: Targets the root element, which is usually the `<html>` element. Useful for setting CSS custom properties (variables).

  ```css
  :root {
      --primary-color: #ff6347;
  }
  ```

#### 4. **:link, :visited**
- **Description**: Selects unvisited (`:link`) and visited (`:visited`) links. These pseudo-classes are important for link styling in navigation and menus.
  
  ```css
  a:link {
      color: blue;
  }
  
  a:visited {
      color: purple;
  }
  ```

---

### Conclusion

Pseudo-classes in CSS provide a powerful way to style elements based on their states, positions, or specific characteristics without the need for additional classes or JavaScript. They are commonly used to create interactive and dynamic UIs, enhance accessibility, and improve user experience.
