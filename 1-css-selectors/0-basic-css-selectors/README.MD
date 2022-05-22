# Basic CSS Selectors


## 01. Element Selectors

Element selectors allow you to target matching HTML element types. They’re a very broad, general selector that allows you to style large portions of content with a single selector. The selector ‘p’, for example, would match every paragraph in the corresponding document. This makes them extremely powerful and well suited for handling site-wide styling.

### Syntax

To write an element selector, simply use the corresponding HTML element, minus the brackets. To target all Heading Ones, for example, you’d simple write h1 instead of ```<h1>```.

```css

h1 {
    color: red;
   }

```

### Example:

This is a paragraph that contains several span tags. I'd like to style these span tags across my entire site at once, to establish a default site-wide format for them. The most efficient selector for this would be the element selector, as it will allow me to establish a base-line format for the span tag with a low degree of specificity. This means that the formatting will be controlled throughout the entire site with a single selector, and it will be easy to overwrite in specific instances where I want the styling to change.
