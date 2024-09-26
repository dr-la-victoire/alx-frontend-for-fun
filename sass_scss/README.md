# SASS & SCSS Guide

## What Sass Means

**Sass (Syntactically Awesome Style Sheets)** is an extension of CSS that adds power and flexibility to the basic language. It allows you to use variables, nested rules, mixins, inheritance, and more, making it easier to write and maintain large stylesheets.

## How to Write Sass & Scss File

Sass can be written in two different syntaxes:

- **SASS (.sass):** A more concise syntax that doesn't use curly braces `{}` or semicolons `;`. It relies on indentation.
- **SCSS (.scss):** A superset of CSS, meaning any valid CSS code is also valid SCSS. It uses traditional CSS syntax with curly braces and semicolons.

### Sass Example:

```sass
$primary-color: blue

.button
  background-color: $primary-color
  color: white
  &:hover
    background-color: darkblue
```

### SCSS Example:

```scss
$primary-color: blue;

.button {
  background-color: $primary-color;
  color: white;
  &:hover {
    background-color: darkblue;
  }
}
```

## What is the Difference Between Sass and Scss?

- **SASS:** Uses a more concise, indentation-based syntax and does not require curly braces or semicolons.
- **SCSS:** Uses the same syntax as CSS with the addition of Sass features. It requires curly braces and semicolons, making it easier for developers familiar with CSS to learn.

## What is Sass Preprocessing?

Sass is a preprocessor, which means it takes the `.sass` or `.scss` file and compiles it into standard CSS that browsers can understand. This preprocessing step allows you to write more dynamic and maintainable styles with features like variables, mixins, and nested rules, which are not available in vanilla CSS.

## How to Declare a Variable

In Sass, you can declare variables to store values like colors, fonts, or any CSS value that you might reuse throughout the stylesheet.

### Example:

```scss
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font-family: $font-stack;
  color: $primary-color;
}
```

## How to Use Nested Definitions

Nesting allows you to write styles in a hierarchical manner, keeping related styles grouped together.

### Example:

```scss
.navbar {
  background-color: #333;

  .nav-item {
    color: white;
    &:hover {
      color: lightgray;
    }
  }
}
```

## How to Import a Sass File

You can split your styles into smaller, manageable files and use `@import` to include them into a main Sass file.

### Example:

```scss
// _variables.scss
$primary-color: blue;
$secondary-color: green;

// main.scss
@import "variables";

body {
  background-color: $primary-color;
}
```

## How to Use Mixins

Mixins allow you to define reusable chunks of CSS code that can be included wherever needed.

### Example:

```scss
@mixin button-styles($color) {
  background-color: $color;
  border-radius: 5px;
  padding: 10px 15px;
}

.button {
  @include button-styles(blue);
}
```

## How to Declare Extend/Inheritance Styles

Inheritance in Sass allows you to share a set of CSS properties from one selector to another using `@extend`.

### Example:

```scss
.alert {
  padding: 10px;
  border: 1px solid red;
  background-color: pink;
}

.error {
  @extend .alert;
  border-color: darkred;
}
```

## How to Manipulate Operators

Sass allows you to perform mathematical operations like addition, subtraction, multiplication, and division directly in your stylesheets.

### Example:

```scss
$base-padding: 10px;

.container {
  padding: $base-padding * 2; // Resulting padding: 20px
}

.box {
  width: 100% / 3; // Resulting width: 33.3333%
}
```

---
