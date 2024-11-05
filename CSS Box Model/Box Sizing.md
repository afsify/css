# Box Sizing in CSS

The `box-sizing` property in CSS determines how the width and height of an element are calculated, particularly how padding and borders are included in those dimensions. It plays a critical role in designing layouts and controlling the sizing of elements.

### Values

There are three primary values for the `box-sizing` property:

1. **content-box** (default)
2. **border-box**
3. **inherit**

### 1. **content-box**

**Description**: This is the default value for the `box-sizing` property. The width and height of the element are calculated only based on the content. Padding and borders are added to the width and height, resulting in an increased total size of the box.

**Syntax**:
```css
box-sizing: content-box;
```

**Example**:
```html
<div style="width: 200px; height: 100px; padding: 20px; border: 5px solid black; box-sizing: content-box;">
    Content Box
</div>
```
- **Total Width**: `200px (width) + 20px (left padding) + 20px (right padding) + 5px (left border) + 5px (right border) = 250px`
- **Total Height**: `100px (height) + 20px (top padding) + 20px (bottom padding) + 5px (top border) + 5px (bottom border) = 150px`

### 2. **border-box**

**Description**: When `box-sizing` is set to `border-box`, the width and height of the element include the content, padding, and border. This means that the total size of the box remains as specified, making it easier to design layouts without worrying about extra padding and border sizes.

**Syntax**:
```css
box-sizing: border-box;
```

**Example**:
```html
<div style="width: 200px; height: 100px; padding: 20px; border: 5px solid black; box-sizing: border-box;">
    Border Box
</div>
```
- **Total Width**: `200px` (includes padding and border)
- **Total Height**: `100px` (includes padding and border)

### 3. **inherit**

**Description**: The `inherit` value makes the element inherit the `box-sizing` property value from its parent element.

**Syntax**:
```css
box-sizing: inherit;
```

**Example**:
```html
<div style="box-sizing: border-box;">
    <div style="box-sizing: inherit; width: 100px; height: 100px; padding: 10px; border: 5px solid black;">
        Inherit Box Sizing
    </div>
</div>
```
- The inner `div` inherits the `border-box` sizing from the outer `div`.

### Global Box Sizing

A common practice in modern CSS is to set `box-sizing` globally to `border-box`. This approach simplifies layout calculations and is recommended for consistent design.

**Example of Global Box Sizing**:
```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

### Summary of Key Concepts

- **Box Sizing**: Controls how the width and height of an element are calculated.
- **content-box**: Default value; width/height do not include padding or borders.
- **border-box**: Width/height include padding and borders; simplifies layout design.
- **inherit**: Element inherits the `box-sizing` value from its parent.

By using the `box-sizing` property effectively, you can manage the sizing of elements in a more predictable way, enhancing your ability to create visually appealing layouts in CSS.