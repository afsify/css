# Transform Origin

**Definition**: The `transform-origin` property in CSS defines the point around which a transformation (like rotation, scaling, or skewing) is applied. By default, transformations occur around the center of an element, but with `transform-origin`, you can change this point to any part of the element.

### Syntax

```css
transform-origin: x-axis y-axis;
```

- **x-axis**: Specifies the horizontal position of the transform origin. Values can be specified in pixels, percentages, or keywords (`left`, `center`, `right`).
- **y-axis**: Specifies the vertical position of the transform origin. Like the x-axis, values can be in pixels, percentages, or keywords (`top`, `center`, `bottom`).
- **z-axis**: (optional) Used in 3D transformations to specify the depth point.

### Default Value
By default, the `transform-origin` is set to `50% 50%`, which means the transformation will be applied around the center of the element.

### Usage of `transform-origin`

The `transform-origin` property is especially useful when you apply transformations like `rotate`, `scale`, or `skew` because it defines the pivot point. Changing the transform origin affects how the transformation behaves.

### Common Keywords

- **`left`**: 0% (aligns to the left edge of the element)
- **`center`**: 50% (aligns to the center of the element, default)
- **`right`**: 100% (aligns to the right edge of the element)
- **`top`**: 0% (aligns to the top edge of the element)
- **`bottom`**: 100% (aligns to the bottom edge of the element)

You can combine these keywords to define specific points in the element's box, such as `top left`, `center right`, or `bottom center`.

### Values

1. **Percentages**:
   - `transform-origin: 100% 100%`: This would place the origin at the bottom-right corner.
   - `transform-origin: 0% 0%`: This places the origin at the top-left corner.

2. **Length units**:
   - `transform-origin: 10px 20px`: The origin is placed 10px from the left and 20px from the top of the element.

3. **Combination of keywords**:
   - `transform-origin: top left`: The origin is at the top-left corner.
   - `transform-origin: bottom center`: The origin is at the bottom center of the element.

4. **Z-axis (for 3D Transforms)**:
   - `transform-origin: 50% 50% 100px`: For 3D transforms, you can specify a z-axis to control depth. The value here moves the origin 100px along the Z-axis (toward or away from the viewer).

### Examples

#### 1. **Rotation Around Different Points**

If you want to rotate an element around a corner instead of the center:

```css
.element {
    width: 100px;
    height: 100px;
    background-color: red;
    transform-origin: top left;
    transform: rotate(45deg);
}
```

- **Explanation**: The rotation will occur around the top-left corner of the element instead of the default center.

#### 2. **Scaling an Element with Different Origin**

If you want to scale an element from the bottom-right corner:

```css
.element {
    width: 100px;
    height: 100px;
    background-color: blue;
    transform-origin: bottom right;
    transform: scale(2);
}
```

- **Explanation**: The element will scale up, but the bottom-right corner will remain in the same position, and the element will grow outward from there.

#### 3. **Using Percentages for Precision**

```css
.element {
    width: 100px;
    height: 100px;
    background-color: green;
    transform-origin: 20% 80%;
    transform: rotate(45deg);
}
```

- **Explanation**: The rotation happens with the origin positioned at 20% from the left and 80% from the top, creating an interesting angle and rotation effect.

#### 4. **3D Transformations with Z-Axis**

```css
.element {
    width: 100px;
    height: 100px;
    background-color: purple;
    transform-origin: center center 50px;
    transform: rotateX(45deg);
}
```

- **Explanation**: Here, the transformation is a 3D rotation around the `X-axis`. The origin is moved 50px towards the viewer on the Z-axis, which alters the perspective of the rotation.

### Interaction with Other CSS Transformations

`transform-origin` works in conjunction with other `transform` functions like `rotate`, `scale`, `skew`, and `translate`. The point defined by `transform-origin` is used as the pivot for the transformation.

For example:
```css
.element {
    transform-origin: center;
    transform: rotate(45deg) scale(1.5);
}
```
- The element rotates 45 degrees and scales 1.5 times, with the center of the element as the pivot.

### Best Practices

1. **Use on Animated Elements**: It’s common to animate elements with different `transform-origin` values to create interesting effects, such as rotating an image around a corner during hover.

2. **Combine with Transition**: You can use `transform-origin` with CSS transitions to create smooth animations:
   ```css
   .element {
       transition: transform-origin 0.3s ease-in-out;
   }
   .element:hover {
       transform-origin: top right;
   }
   ```

3. **3D Effects**: In 3D designs, manipulating the `z-axis` of `transform-origin` can create a more immersive and dynamic effect.

### Conclusion

The `transform-origin` property provides fine control over how transformations are applied to elements. By changing the origin point, you can control the pivot for rotations, scaling, and other transformations, allowing for more creative and precise animations and layouts. Using `transform-origin` effectively can make your animations and transformations feel more natural, responsive, and visually engaging.
