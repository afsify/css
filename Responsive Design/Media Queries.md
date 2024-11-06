# Media Queries in CSS

Media queries are a CSS feature that allows you to apply specific styles depending on the characteristics of the user’s device, such as screen size, orientation, or resolution. They are crucial for creating responsive designs that adapt to different screen sizes, making them suitable for desktops, tablets, and mobile devices.

### Syntax of Media Queries

Media queries use the `@media` rule in CSS. Basic syntax:

```css
@media (condition) {
    /* CSS rules go here */
}
```

### Common Media Query Conditions

1. **Width-Based Media Queries**
   - `min-width`: Applies styles if the viewport width is **greater than or equal** to the specified value.
   - `max-width`: Applies styles if the viewport width is **less than or equal** to the specified value.

   ```css
   /* For screens at least 768px wide */
   @media (min-width: 768px) {
       /* CSS rules */
   }

   /* For screens up to 768px wide */
   @media (max-width: 768px) {
       /* CSS rules */
   }
   ```

2. **Height-Based Media Queries**
   - `min-height`: Applies styles if the viewport height is **greater than or equal** to the specified value.
   - `max-height`: Applies styles if the viewport height is **less than or equal** to the specified value.

   ```css
   /* For viewports at least 500px in height */
   @media (min-height: 500px) {
       /* CSS rules */
   }
   ```

3. **Orientation-Based Media Queries**
   - `orientation`: Targets devices in either `landscape` or `portrait` mode.

   ```css
   /* For landscape mode */
   @media (orientation: landscape) {
       /* CSS rules */
   }

   /* For portrait mode */
   @media (orientation: portrait) {
       /* CSS rules */
   }
   ```

4. **Resolution-Based Media Queries**
   - `resolution`: Targets devices based on the display resolution (DPI or DPCM).

   ```css
   /* For high-resolution screens */
   @media (min-resolution: 192dpi) {
       /* CSS rules */
   }
   ```

5. **Aspect-Ratio-Based Media Queries**
   - `aspect-ratio`: Targets devices based on the ratio of the width to the height.

   ```css
   /* For screens with a 16:9 aspect ratio */
   @media (aspect-ratio: 16/9) {
       /* CSS rules */
   }
   ```

### Combining Media Queries

Media queries can be combined using `and`, `or`, and `not` operators:

- **Using `and`**: Both conditions must be true for the styles to apply.
  ```css
  @media (min-width: 768px) and (orientation: portrait) {
      /* CSS rules */
  }
  ```

- **Using `or` (comma separated)**: Styles apply if **any** condition is true.
  ```css
  @media (max-width: 480px), (orientation: landscape) {
      /* CSS rules */
  }
  ```

- **Using `not`**: Negates the condition.
  ```css
  @media not (min-width: 1024px) {
      /* CSS rules */
  }
  ```

### Practical Examples of Media Queries

1. **Responsive Font Size**

   ```css
   body {
       font-size: 16px;
   }

   @media (min-width: 768px) {
       body {
           font-size: 18px;
       }
   }

   @media (min-width: 1024px) {
       body {
           font-size: 20px;
       }
   }
   ```

2. **Responsive Grid Layout**

   ```css
   .container {
       display: grid;
       grid-template-columns: 1fr;
   }

   @media (min-width: 600px) {
       .container {
           grid-template-columns: 1fr 1fr; /* Two-column layout */
       }
   }

   @media (min-width: 1024px) {
       .container {
           grid-template-columns: 1fr 1fr 1fr; /* Three-column layout */
       }
   }
   ```

3. **Responsive Navigation Menu**

   ```css
   .nav-menu {
       display: flex;
       flex-direction: column;
   }

   @media (min-width: 768px) {
       .nav-menu {
           flex-direction: row; /* Horizontal menu on larger screens */
       }
   }
   ```

### Breakpoints for Responsive Design

Breakpoints are specific viewport widths where styles change to accommodate different screen sizes. Common breakpoints include:

- **Mobile**: `0px` to `767px`
- **Tablet**: `768px` to `1023px`
- **Desktop**: `1024px` and above

Example of breakpoints:

```css
/* Mobile styles */
@media (max-width: 767px) {
    /* CSS rules */
}

/* Tablet styles */
@media (min-width: 768px) and (max-width: 1023px) {
    /* CSS rules */
}

/* Desktop styles */
@media (min-width: 1024px) {
    /* CSS rules */
}
```

### Tips for Using Media Queries

1. **Mobile-First Approach**: Start by designing for mobile devices, then add media queries for larger screens.
2. **Use Flexible Units**: Use relative units like `em` or `rem` for better scaling across devices.
3. **Minimize Repetition**: Only override properties that need to change. Avoid duplicating CSS rules.
4. **Test Responsiveness**: Check how your site looks on different devices and screen sizes.

### Summary

Media queries are essential for creating adaptive layouts that provide an optimal viewing experience across a wide range of devices. They allow you to control layout, typography, and other design aspects according to the characteristics of each user’s device.
