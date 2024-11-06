# CSS Transitions

CSS Transitions make it easy to animate changes to CSS properties, creating smooth effects when elements go from one state to another. They are triggered by changes such as hover, focus, active, or any other state that modifies CSS properties.

### Basic Syntax of Transitions

The `transition` property is shorthand for setting multiple transition properties simultaneously. The syntax:

```css
transition: property duration timing-function delay;
```

- **property**: The CSS property you want to animate (e.g., `color`, `background-color`, `width`). Use `all` to apply transitions to all properties that change.
- **duration**: How long the transition takes (e.g., `0.5s`, `200ms`).
- **timing-function**: Controls the speed curve (e.g., `ease`, `linear`, `ease-in`, `ease-out`).
- **delay**: The delay before the transition starts (optional, e.g., `0s`, `200ms`).

### Example

```css
.button {
    background-color: blue;
    color: white;
    transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
}

.button:hover {
    background-color: white;
    color: blue;
}
```

In this example, the background and text color of `.button` will transition smoothly when hovered.

### Transition Properties

1. **transition-property**
   - Specifies which CSS properties will have transitions.
   - Values: Specific properties (e.g., `width`, `color`) or `all`.

   ```css
   transition-property: color;
   ```

2. **transition-duration**
   - Defines how long the transition takes.
   - Value is specified in seconds (`s`) or milliseconds (`ms`).

   ```css
   transition-duration: 0.5s;
   ```

3. **transition-timing-function**
   - Sets the speed curve of the transition, controlling acceleration and deceleration.
   - Common values:
     - **linear**: Constant speed.
     - **ease**: Slow start, then fast, then slow end.
     - **ease-in**: Starts slow and speeds up.
     - **ease-out**: Starts fast and slows down.
     - **ease-in-out**: Starts and ends slowly.

   ```css
   transition-timing-function: ease-in-out;
   ```

4. **transition-delay**
   - Defines a delay before the transition starts.
   - Value is specified in seconds or milliseconds.

   ```css
   transition-delay: 0.2s;
   ```

### Shorthand Example

```css
/* Apply transition to color, with duration, timing-function, and delay */
.element {
    transition: color 0.4s ease 0.1s;
}
```

### Practical Examples of CSS Transitions

1. **Background Color Transition**

   ```css
   .box {
       background-color: #3498db;
       transition: background-color 0.5s ease;
   }

   .box:hover {
       background-color: #2ecc71;
   }
   ```

2. **Width Transition**

   ```css
   .expandable {
       width: 100px;
       transition: width 0.4s ease-in-out;
   }

   .expandable:hover {
       width: 200px;
   }
   ```

3. **Opacity Transition**

   ```css
   .fade {
       opacity: 1;
       transition: opacity 0.3s ease-out;
   }

   .fade:hover {
       opacity: 0.5;
   }
   ```

4. **Multiple Transitions**

   ```css
   .card {
       background-color: #fff;
       color: #333;
       transform: scale(1);
       transition: background-color 0.3s, color 0.3s, transform 0.3s;
   }

   .card:hover {
       background-color: #333;
       color: #fff;
       transform: scale(1.05);
   }
   ```

### Using Transition with `all`

You can apply transitions to all properties that change by setting `transition-property: all;`, but this approach can sometimes be inefficient and is best used selectively.

```css
.element {
    transition: all 0.5s ease;
}

.element:hover {
    background-color: pink;
    transform: scale(1.1);
}
```

### Timing Functions and Custom Cubic Bezier

The **cubic-bezier** function allows for custom timing functions with four values, giving full control over the transition’s pace.

```css
.element {
    transition: transform 0.6s cubic-bezier(0.25, 1, 0.5, 1);
}

.element:hover {
    transform: scale(1.2);
}
```

### Tips for Using Transitions

- **Keep it Simple**: Use transitions for subtle effects rather than complex animations.
- **Avoid Overuse**: Too many transitions on a page can impact performance.
- **Combine with Hover, Focus, and Active States**: Transitions work well with interactive states for a polished user experience.
- **Test on Different Devices**: Check that transitions work smoothly on both desktop and mobile.

### Summary

CSS Transitions add visual appeal and smoothness to interactions, making websites feel more dynamic. By adjusting duration, timing, and delay, you can create polished, user-friendly effects with minimal CSS.

---

These notes should help you implement and understand CSS transitions effectively. Let me know if you need more examples!