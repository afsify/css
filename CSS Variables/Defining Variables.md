# Defining CSS Variables: Using `--variable-name`

CSS variables, also known as **custom properties**, allow you to define values that can be reused throughout your CSS. These variables are defined using a `--` prefix and are particularly useful for making your CSS more maintainable, especially when you need to manage repeated values (like colors, font sizes, or spacing) across a large stylesheet.

---

### 1. **What Are CSS Variables?**

A **CSS variable** is a user-defined property whose value can be reused throughout a stylesheet. These variables allow you to store values and easily update them in one place, avoiding duplication and making it easier to manage your styles.

---

### 2. **Defining CSS Variables**

CSS variables are defined within a selector, typically under the `:root` pseudo-class, which applies to the entire document, or within specific elements.

#### **Basic Syntax**
```css
--variable-name: value;
```
- The variable name must start with `--` and be followed by a name of your choice (e.g., `--primary-color`).
- The value assigned can be any valid CSS value (e.g., color, length, font, etc.).

#### Example:
```css
:root {
    --primary-color: #3498db;
    --font-size: 16px;
    --padding: 10px;
}
```
In this example:
- `--primary-color` stores the blue color code `#3498db`.
- `--font-size` stores the value `16px`.
- `--padding` stores the value `10px`.

---

### 3. **Using CSS Variables**

Once a variable is defined, you can use it in your CSS by referencing it with the `var()` function.

#### **Syntax to Use a Variable**
```css
property: var(--variable-name);
```

#### Example:
```css
body {
    font-size: var(--font-size);
    background-color: var(--primary-color);
    padding: var(--padding);
}
```

In this example:
- `font-size` is set to the value of `--font-size` (16px).
- `background-color` is set to the value of `--primary-color` (`#3498db`).
- `padding` is set to the value of `--padding` (10px).

---

### 4. **Scope of CSS Variables**

CSS variables can have different scopes, depending on where they are defined.

#### **Global Scope** (Using `:root`)

When a variable is defined under `:root`, it is available globally across the entire document.

```css
:root {
    --main-bg-color: lightgrey;
}

body {
    background-color: var(--main-bg-color);  /* lightgrey */
}
```

#### **Local Scope**

You can define variables within specific elements, making them available only to that element and its descendants.

```css
.card {
    --card-bg-color: #fff;
    background-color: var(--card-bg-color);  /* white */
}

.card-dark {
    --card-bg-color: #333;
    background-color: var(--card-bg-color);  /* dark grey */
}
```

In this example:
- The `.card` class has its own local `--card-bg-color` variable.
- `.card-dark` has a different value for `--card-bg-color`, making the background dark.

---

### 5. **Fallback Values**

You can provide fallback values when using `var()` in case the variable is not defined or has an invalid value.

#### **Syntax with Fallback**
```css
property: var(--variable-name, fallback-value);
```

#### Example:
```css
button {
    color: var(--button-text-color, black);  /* Default to black if --button-text-color is not defined */
}
```
In this example:
- If `--button-text-color` is not defined, the button will default to `black`.

---

### 6. **Updating CSS Variables with JavaScript**

CSS variables can be dynamically changed with JavaScript, making them very powerful for creating interactive, themeable UIs.

#### Example: Changing a Variable Using JavaScript
```javascript
document.documentElement.style.setProperty('--primary-color', '#e74c3c');
```
This JavaScript code changes the value of `--primary-color` to `#e74c3c`, which would affect any styles using that variable.

---

### 7. **Advantages of Using CSS Variables**

1. **Reusability**: Define values once and reuse them throughout the stylesheet.
2. **Maintainability**: When you need to update a value, you only need to do it in one place.
3. **Dynamic Styling**: Variables can be dynamically changed using JavaScript for themes or interactive effects.
4. **Inheritance**: CSS variables can be inherited, making them useful for cascading values across elements.
5. **Fallback Mechanism**: You can provide fallback values, ensuring a graceful fallback when a variable is missing.

---

### 8. **Example Use Cases for CSS Variables**

#### **Theme Switching**
CSS variables are perfect for implementing dark and light modes. You can define different values for each theme and switch them dynamically.

##### Example:
```css
:root {
    --background-light: #fff;
    --background-dark: #333;
    --text-light: #000;
    --text-dark: #fff;
}

body.light-mode {
    background-color: var(--background-light);
    color: var(--text-light);
}

body.dark-mode {
    background-color: var(--background-dark);
    color: var(--text-dark);
}
```
JavaScript can be used to toggle between `light-mode` and `dark-mode` classes, dynamically changing the styles.

---

### 9. **Browser Support**

CSS variables are widely supported in modern browsers, including Chrome, Firefox, Safari, Edge, and Opera. However, they are not supported in Internet Explorer. It's important to consider this when designing for older browsers.

---

### Conclusion

CSS variables (`--variable-name`) offer a flexible and powerful way to manage and reuse values throughout your stylesheets. They make your CSS more maintainable, and their ability to change dynamically via JavaScript allows for responsive and interactive design elements like theme switching and dynamic styling.
