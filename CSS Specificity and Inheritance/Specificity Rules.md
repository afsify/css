# Specificity Rules: ID, Class, and Element Specificity in CSS

**CSS specificity** determines which styles are applied to an element when multiple CSS rules target the same element. Specificity is calculated based on a system of rules that prioritize the more specific selector over less specific ones. This ensures that the style with higher specificity overrides styles with lower specificity.

### 1. **What is Specificity?**

Specificity is a ranking system that browsers use to determine which styles to apply when multiple rules could target the same element. The more specific a selector is, the higher its specificity score, and the more likely it is to be applied.

Specificity is calculated using a **four-value system**: 

- **Inline styles** (added directly to the element via the `style` attribute) have the highest specificity.
- **IDs** are more specific than classes and elements.
- **Classes, attributes, and pseudo-classes** have higher specificity than elements.
- **Element selectors and pseudo-elements** have the lowest specificity.

### 2. **Specificity Calculation**

Specificity is calculated by breaking a CSS selector into four parts:

- **A**: The number of inline styles (not used often but has the highest priority).
- **B**: The number of IDs in the selector.
- **C**: The number of classes, attributes, and pseudo-classes in the selector.
- **D**: The number of element selectors and pseudo-elements in the selector.

The specificity score is written as a four-part value `(A, B, C, D)`.

### 3. **Specificity Hierarchy**

1. **Inline styles** (highest specificity):
   - Example: `<div style="color: red;">`
   - Specificity: `(1, 0, 0, 0)`
   - Inline styles will always override styles defined in external stylesheets.
   
2. **IDs**:
   - Example: `#header`
   - Specificity: `(0, 1, 0, 0)`
   - An ID selector is more specific than a class or element selector. It is often used for unique elements on a page.

3. **Classes, attributes, and pseudo-classes**:
   - Example: `.navbar`, `[type="text"]`, `:hover`
   - Specificity: `(0, 0, 1, 0)`
   - These selectors are more specific than element selectors but less specific than ID selectors.

4. **Elements and pseudo-elements** (lowest specificity):
   - Example: `div`, `h1`, `p`, `::before`
   - Specificity: `(0, 0, 0, 1)`
   - These are the most general and are overridden by other selectors like classes and IDs.

### 4. **Example of Specificity Calculation**

Let’s consider an example where multiple rules target the same element.

```html
<p id="header" class="title" style="color: red;">Hello World!</p>
```

The following CSS rules are applied:

```css
p {
  color: blue;
}

.title {
  color: green;
}

#header {
  color: yellow;
}
```

In this case, the **specificity** of each selector is:

- `p`: Specificity = `(0, 0, 0, 1)` (element selector)
- `.title`: Specificity = `(0, 0, 1, 0)` (class selector)
- `#header`: Specificity = `(0, 1, 0, 0)` (ID selector)

**Resolution**: The `#header` rule will be applied because IDs have the highest specificity. Despite the inline style setting `color: red;`, the inline styles have the highest priority and would override any CSS rule if specified. So, in this case, `color: yellow;` will be the applied color.

---

### 5. **Specificity Conflicts: Cascade Rule**

When two rules with equal specificity conflict, the **last rule** declared in the CSS will be applied.

For example, if we have these conflicting rules:

```css
.title {
  color: green;
}

.title {
  color: blue;
}
```

Both have the same specificity, but because the second rule is declared last, it will be applied, and the text will be `blue`.

---

### 6. **Key Concepts in Specificity**

#### **6.1. Universal Selector `*`**
The universal selector `*` has the lowest specificity and is overridden by any other selector, including class and ID selectors.

```css
* {
  color: black;
}

.title {
  color: green;
}
```

**Result**: `.title` will override the universal selector because `.title` has higher specificity.

#### **6.2. Attribute Selectors**
Attribute selectors have the same specificity as class selectors.

```css
input[type="text"] {
  border: 1px solid red;
}
```

This has the same specificity as a class selector and is more specific than an element selector.

#### **6.3. Pseudo-classes**
Pseudo-classes such as `:hover`, `:focus`, or `:first-child` have higher specificity than element selectors but lower specificity than class or ID selectors.

```css
a:hover {
  color: blue;
}
```

This selector is more specific than just an `a` tag but less specific than `.link` or `#header`.

---

### 7. **Practical Use of Specificity**

- **Avoid Overuse of IDs**: IDs should be used sparingly because they are very specific. Overusing them can make it difficult to override styles in larger projects.
- **Use Classes for Grouping**: Use classes for grouping elements with similar styles, as they are more flexible than IDs and have a moderate specificity.
- **Avoid Inline Styles**: Inline styles have the highest specificity and override other styles, which makes it difficult to maintain and debug.

---

### 8. **Summary of Specificity Hierarchy (Highest to Lowest)**

| **Specificity**        | **Type**                       | **Example**         | **Specificity Value**  |
|------------------------|--------------------------------|---------------------|------------------------|
| **Highest**            | Inline Styles                  | `<div style="color: red;">` | `(1, 0, 0, 0)`         |
| **Very High**          | ID Selector                    | `#header`           | `(0, 1, 0, 0)`         |
| **Moderate**           | Class, Attribute, Pseudo-classes | `.navbar`, `[type="text"]`, `:hover` | `(0, 0, 1, 0)`         |
| **Low**                | Element Selector               | `div`, `h1`, `p`    | `(0, 0, 0, 1)`         |
| **Lowest**             | Universal Selector             | `*`                 | `(0, 0, 0, 0)`         |

### Conclusion

Understanding CSS specificity helps you write more predictable and maintainable styles. By knowing how specificity works, you can avoid conflicts between styles, and ensure that the desired rules are applied correctly. Always remember the order of specificity from inline styles (most specific) to element selectors (least specific).
