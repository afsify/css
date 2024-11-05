# Z-Index and Stacking Contexts

### Z-Index

**Description**: The `z-index` property in CSS controls the vertical stacking order of elements that overlap. It determines which element appears on top of others when they occupy the same space in a layout.

### Syntax

```css
element {
    z-index: value; /* value can be an integer (positive, negative, or zero) */
}
```

### Key Points

- The `z-index` property only applies to positioned elements (elements with a position value of `relative`, `absolute`, `fixed`, or `sticky`).
- Elements with a higher `z-index` value will appear on top of those with a lower value.
- If two elements have the same `z-index`, the one that appears later in the HTML document will be on top.

### Values

1. **Integer Values**: 
   - Positive integers stack elements higher (e.g., `z-index: 10;`).
   - Negative integers stack elements lower (e.g., `z-index: -1;`).
   - A `z-index` value of `0` places an element at the default stacking level.

2. **Auto**: 
   - The default value of `z-index`. Elements will stack based on their order in the HTML document.

### Example

```html
<div class="box-1">Box 1</div>
<div class="box-2">Box 2</div>
```
```css
.box-1 {
    position: relative;
    z-index: 1;
    background: lightblue;
    width: 100px;
    height: 100px;
}

.box-2 {
    position: relative;
    z-index: 2; /* This will appear on top of box-1 */
    background: lightcoral;
    width: 100px;
    height: 100px;
    margin-top: -50px; /* Move it up to overlap box-1 */
}
```

### Stacking Contexts

**Description**: A stacking context is a three-dimensional conceptualization of HTML elements along the z-axis (depth). It determines the stacking order of elements and how they interact with `z-index`.

### When a Stacking Context is Created

A new stacking context is created in the following situations:

1. **Root Element**: The root element of the document (`<html>`) always creates a stacking context.
2. **Positioned Elements**: Elements with a position value of `absolute`, `relative`, `fixed`, or `sticky` and a `z-index` value other than `auto`.
3. **Certain CSS Properties**: Elements with specific CSS properties can create a stacking context, including:
   - `opacity` less than 1
   - `transform` (other than `none`)
   - `filter` (other than `none`)
   - `perspective` (other than `none`)
   - `clip-path` (other than `none`)
   - `mask` (other than `none`)
   - `contain` property set to `layout`, `style`, or `paint`
   - `will-change` property with values like `transform`, `opacity`, etc.

### Example of Stacking Contexts

```html
<div class="parent">
    <div class="child-1">Child 1</div>
    <div class="child-2">Child 2</div>
</div>
```
```css
.parent {
    position: relative; /* Creates a new stacking context */
    z-index: 1; /* This parent creates its own stacking context */
}

.child-1 {
    position: absolute; /* Positioned child */
    z-index: 2; /* Higher z-index within its stacking context */
    background: lightgreen;
    width: 100px;
    height: 100px;
}

.child-2 {
    position: absolute; /* Positioned child */
    z-index: 1; /* Lower z-index within its stacking context */
    background: lightpink;
    width: 100px;
    height: 100px;
    margin-left: 50px; /* Move it to overlap */
}
```

In this example, even though `child-1` has a higher `z-index`, it is still contained within the stacking context of the `parent` div. Elements outside this context can have their own `z-index` values that may affect how these children stack against other elements in the DOM.

### Best Practices

1. **Use Z-Index Judiciously**: Overusing `z-index` can make your layout complex and harder to manage. Keep stacking contexts to a minimum.
2. **Plan Stacking Contexts**: Understand how stacking contexts are created to avoid unexpected results in your layouts.
3. **Debugging**: Use browser developer tools to visualize stacking contexts and understand how `z-index` values are applied in your layout.
4. **Avoid Negative Z-Index**: Be cautious with negative values; they can cause elements to become inaccessible or hidden behind other elements unintentionally.
5. **Hierarchy Awareness**: Always remember that `z-index` only works within the same stacking context; elements in different contexts do not affect each other's stacking order.

By understanding `z-index` and stacking contexts, you can effectively manage how elements overlap and interact in your web designs, leading to a more organized and visually appealing layout.