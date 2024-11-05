# Text Properties in CSS

Text properties in CSS control the appearance and layout of text within HTML elements. They include properties for font styling, alignment, decoration, spacing, and more.

---

### 1. Font Properties

- **`font-family`**: Specifies the typeface to be used for the text.
  ```css
  p {
      font-family: 'Arial', sans-serif; /* Fallback to sans-serif if Arial is unavailable */
  }
  ```

- **`font-size`**: Sets the size of the font.
  ```css
  h1 {
      font-size: 24px; /* 24 pixels */
  }
  ```

- **`font-weight`**: Defines the thickness of the font characters.
  ```css
  strong {
      font-weight: bold; /* Can also use numeric values like 400 (normal), 700 (bold) */
  }
  ```

- **`font-style`**: Applies italic or oblique styles to the text.
  ```css
  em {
      font-style: italic; /* Italic style */
  }
  ```

- **`font-variant`**: Controls the use of small caps.
  ```css
  .small-caps {
      font-variant: small-caps; /* Small caps text */
  }
  ```

- **`font-size-adjust`**: Allows for the adjustment of the font size based on the aspect ratio of the font.
  ```css
  body {
      font-size-adjust: 0.5; /* Maintain a good visual size ratio */
  }
  ```

---

### 2. Text Alignment

- **`text-align`**: Specifies the horizontal alignment of text within an element.
  ```css
  .centered {
      text-align: center; /* Center-align text */
  }
  ```

- **`text-justify`**: Specifies the justification of text when text-align is set to `justify`.
  ```css
  p {
      text-align: justify; /* Justified text */
      text-justify: inter-word; /* Adjust spaces between words */
  }
  ```

---

### 3. Text Decoration

- **`text-decoration`**: Adds decoration to text such as underline, overline, or line-through.
  ```css
  a {
      text-decoration: underline; /* Underlined text */
  }
  ```

- **`text-decoration-color`**: Sets the color of the text decoration.
  ```css
  a {
      text-decoration: underline;
      text-decoration-color: red; /* Red underline */
  }
  ```

- **`text-decoration-style`**: Defines the style of the text decoration (solid, double, dotted, etc.).
  ```css
  a {
      text-decoration: underline;
      text-decoration-style: dashed; /* Dashed underline */
  }
  ```

---

### 4. Text Transformation

- **`text-transform`**: Controls the capitalization of text.
  ```css
  h2 {
      text-transform: uppercase; /* Converts text to uppercase */
  }
  ```

---

### 5. Text Spacing

- **`letter-spacing`**: Adjusts the space between characters in text.
  ```css
  h1 {
      letter-spacing: 2px; /* 2 pixels of space between letters */
  }
  ```

- **`line-height`**: Sets the height of a line box, affecting the space between lines of text.
  ```css
  p {
      line-height: 1.5; /* 1.5 times the font size */
  }
  ```

- **`word-spacing`**: Adjusts the space between words.
  ```css
  p {
      word-spacing: 5px; /* 5 pixels of space between words */
  }
  ```

---

### 6. Text Shadow

- **`text-shadow`**: Adds a shadow effect to text.
  ```css
  h1 {
      text-shadow: 2px 2px 5px gray; /* 2px right and down, 5px blur radius */
  }
  ```

---

### 7. White Space Handling

- **`white-space`**: Controls how whitespace inside an element is handled.
  ```css
  pre {
      white-space: pre; /* Preserves whitespace and line breaks */
  }
  ```

- **Values**:
  - `normal`: Collapses whitespace.
  - `nowrap`: Prevents wrapping to a new line.
  - `pre`: Preserves spaces and line breaks.
  - `pre-wrap`: Preserves spaces but allows wrapping.

---

### 8. Direction and Writing Mode

- **`direction`**: Defines the text direction (e.g., left-to-right or right-to-left).
  ```css
  .rtl {
      direction: rtl; /* Right-to-left text direction */
  }
  ```

- **`writing-mode`**: Defines the text orientation and flow direction.
  ```css
  .vertical {
      writing-mode: vertical-rl; /* Vertical text from right to left */
  }
  ```

---

### 9. Practical Examples

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Text Properties Example</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
        }
        h1 {
            font-size: 32px;
            text-align: center;
            text-shadow: 1px 1px 2px gray;
        }
        p {
            line-height: 1.6;
            letter-spacing: 1px;
            word-spacing: 2px;
            text-decoration: underline;
            text-transform: capitalize;
        }
    </style>
</head>
<body>
    <h1>Text Properties Example</h1>
    <p>This is an example paragraph demonstrating various text properties.</p>
</body>
</html>
```

---

### Summary of Key Concepts

- **Font Properties**: Control the typeface, size, weight, and style of text.
- **Text Alignment**: Controls the horizontal alignment of text.
- **Text Decoration**: Adds decorations such as underlines and strikethroughs.
- **Text Transformation**: Modifies text capitalization.
- **Text Spacing**: Adjusts the spacing between characters and lines.
- **Text Shadow**: Applies shadow effects to text.
- **White Space Handling**: Controls how whitespace is treated in elements.
- **Direction and Writing Mode**: Defines the flow and orientation of text.

---

These notes cover the essential aspects of text properties in CSS. If you need further details or examples on any specific property, feel free to ask!