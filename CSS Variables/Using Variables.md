# **Using Variables in CSS: `var(--variable-name)`**

### **What Are CSS Variables?**

CSS Variables, also known as **Custom Properties**, allow you to define reusable values that can be applied throughout your CSS. A variable is a name for a value, which you can reference later in your CSS code. This enables more flexible, maintainable, and scalable stylesheets.

### **Why Use CSS Variables?**

- **Reusability**: Store values in variables and use them throughout your stylesheet, ensuring consistency and reducing the chance of errors.
- **Maintainability**: Easily update a variable’s value in one place and have that change propagate throughout your styles.
- **Dynamic Styling**: Variables can be manipulated dynamically using JavaScript, allowing for real-time changes on the webpage.

### **Syntax for Declaring CSS Variables**

A variable is declared using the `--` prefix and can be scoped to specific elements or applied globally.

```css
/* Declaring a global variable */
:root {
    --primary-color: #3498db;
    --font-size: 16px;
}

/* Using the variable */
body {
    background-color: var(--primary-color);
    font-size: var(--font-size);
}
```

- **`:root`**: The `:root` selector is typically used to define global CSS variables. It represents the highest-level element in the document (usually the `<html>` element).
- **`--primary-color`**: This is a custom property (variable) name. The value following the `:` is the value of the variable.

### **Using CSS Variables**

To use a variable, the `var(--variable-name)` function is employed.

```css
element {
    property: var(--variable-name);
}
```

For example:

```css
/* Declare the variable */
:root {
    --main-bg-color: lightgray;
    --font-color: black;
}

/* Use the variable */
div {
    background-color: var(--main-bg-color);
    color: var(--font-color);
}
```

### **CSS Variables and Scope**

CSS variables can be **global** or **local** (scoped).

1. **Global Scope (defined in `:root`)**: The variable is available throughout the entire document.

   ```css
   :root {
       --main-color: #FF5733;
   }

   .header {
       background-color: var(--main-color);
   }

   .footer {
       background-color: var(--main-color);
   }
   ```

2. **Local Scope (defined within an element)**: The variable is only available within the element and its children.

   ```css
   .container {
       --container-bg: #f0f0f0;
       background-color: var(--container-bg);
   }

   .content {
       background-color: var(--container-bg); /* Inherits the value */
   }

   .other-element {
       background-color: #fff; /* Will not inherit the container's value */
   }
   ```

In the example above:
- The `--container-bg` variable is scoped to `.container`, so it is only available within that element (and its children).
- The `.other-element` does not inherit `--container-bg` because it's outside the `.container` scope.

### **Fallback Values**

You can provide fallback values in case the variable is not defined or is invalid. This is done by specifying a default value after the variable name.

```css
div {
    background-color: var(--background-color, #f0f0f0); /* Fallback to #f0f0f0 */
}
```

If `--background-color` is not defined, the background color will default to `#f0f0f0`.

### **Overriding CSS Variables**

Variables can be easily overridden or redefined in specific contexts. This makes it convenient for theming or adapting to different states, screen sizes, or user preferences.

```css
:root {
    --text-color: black;
}

body {
    color: var(--text-color);
}

body.dark-mode {
    --text-color: white;
    background-color: black;
}
```

In this example:
- The default text color is black.
- When the `body` has the `.dark-mode` class, the text color is overridden to white, and the background becomes black.

### **Using CSS Variables for Theming**

You can use CSS variables to implement **dark mode**, **light mode**, or other themes in your website, as variables make it easy to change the entire theme by adjusting a few values.

```css
/* Light theme */
:root {
    --primary-bg: white;
    --primary-text: black;
}

/* Dark theme */
body.dark-theme {
    --primary-bg: #121212;
    --primary-text: white;
}

body {
    background-color: var(--primary-bg);
    color: var(--primary-text);
}
```

Switching the theme can be done via a class toggle (`dark-theme`), which changes the values of the CSS variables, thus altering the theme without needing to modify other CSS rules.

### **CSS Variables in Media Queries**

CSS variables can be used in **media queries** to adjust values based on the viewport size, making responsive design easier.

```css
:root {
    --font-size: 16px;
}

@media (min-width: 768px) {
    :root {
        --font-size: 18px;
    }
}

p {
    font-size: var(--font-size);
}
```

In this example:
- The default font size is `16px`.
- For screen widths greater than or equal to `768px`, the font size is set to `18px`.

### **Using Variables in JavaScript**

CSS variables can also be dynamically updated using JavaScript by manipulating the `style` property of an element or the `document.documentElement` (the `<html>` element).

```javascript
// Changing the value of a CSS variable
document.documentElement.style.setProperty('--primary-color', 'green');
```

In this example:
- The JavaScript code dynamically changes the value of `--primary-color` to green.

### **Advantages of Using CSS Variables**

- **Reusability**: Avoid repeating the same value in multiple places.
- **Maintainability**: Change a single variable’s value to adjust the entire design or theme.
- **Dynamism**: Easily adjust variables at runtime using JavaScript to respond to user preferences or actions (e.g., switching themes).
- **Inheritance**: Variables can inherit values, making it easy to apply changes across elements without affecting their hierarchy.

### **Limitations of CSS Variables**

- **Browser Support**: CSS variables are widely supported in modern browsers, but older browsers like Internet Explorer do not support them.
- **Cannot Be Used in Media Queries as Custom Properties**: Custom properties cannot be used directly in `@media` rules unless they are declared globally or locally in the correct scope.
  
### **Example: Full Example of CSS Variables Usage**

```css
:root {
    --primary-bg-color: #3498db;
    --secondary-bg-color: #2ecc71;
    --font-family: Arial, sans-serif;
    --font-size: 16px;
}

/* Default theme */
body {
    background-color: var(--primary-bg-color);
    font-family: var(--font-family);
    font-size: var(--font-size);
}

button {
    background-color: var(--secondary-bg-color);
    color: white;
    border: none;
    padding: 10px;
}

/* Dark mode theme */
body.dark-mode {
    --primary-bg-color: #2c3e50;
    --secondary-bg-color: #1abc9c;
}
```

Here:
- The `:root` defines several variables for background colors, font family, and font size.
- The `body` and `button` styles reference these variables.
- The `.dark-mode` class overrides the values of the variables, dynamically changing the appearance when added to the body.

---

## Summary

- **CSS Variables** (`var(--variable-name)`) are a way to store reusable values that can be used throughout your CSS.
- They provide flexibility, maintainability, and ease of updating styles.
- Variables can be scoped globally (using `:root`) or locally to specific elements.
- Use `var(--variable-name)` to reference and apply variable values in your styles.
- Variables support fallback values and can be dynamically updated with JavaScript for real-time style changes.
- They can be used in media queries to create responsive designs.
