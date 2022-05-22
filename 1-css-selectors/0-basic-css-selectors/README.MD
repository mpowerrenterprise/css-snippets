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

## 02. Class Selectors

Class selectors match elements based on the contents of an element’s class attribute. The class selector .author, for example, would match any HTML element with the class attribute of “author.” The specific nature of class selectors combined with the ability to apply class attributes to any element makes them an extremely powerful and flexible option for styling. Because they are so easy to use class selectors can occasionally be over-used, resulting in non-semantic code and code that is more difficult to maintain.

### Syntax

Class selectors are written by adding a period (‘.’) prior to the contents of the targeted attribute value, with no whitespace between the two. To make a class selector specific to an element type, add the element type prior to the period with no whitespace. The selector p.summary would match any paragraph with the class attribute of “summary”. Although CSS is not case-sensitive, there are certain use-cases where the styled document may parse classes with case sensitivity. Because of this it’s a good practice to match the case of class values.

```css
.warning {
  color: red;
    }

h1.warning {
  color: red;
    }
```

### Example:

#### Targeting class attributes
In this example I want to target specific class attribute values. Note how the styling is applied regardless of element type. Class selectors are also more specific than element selectors, so they allow us to overwrite the more general styles of element selectors.

#### Using class selectors
They also allow us to target very specific locations or instances by simply applying a class attribute. This is a great way to write styles for specific purposes with a single selector and then apply it whenever needed by adding the appropriate class attribute.

## 03. ID Selectors

ID selectors allow you to target elements with a specific ID attributes. Because ID values may only be used once per page, ID selectors have a higher degree of specificity than class or element selectors. As such care should be taken when using ID selectors as heavy use of them can cause styling conflicts that are difficult to resolve, especially as stylesheets evolve and change over time.

### Syntax

ID selectors are written using the octothorpe character (‘#’) to precede the value of the ID attribute. To target an element with an ID attribute of “special” the selector would read #special. Note the lack of whitespace between the attribute value and the # symbol. You can make an ID selector element-specific by adding an element selector prior to the octothorpe character. h1#special would only match an H1 with the ID attribute of “special.” Although CSS is not case-sensitive, there are certain use-cases where the user agent may parse IDs with case sensitivity. Because of this it’s a good practice to match the case of ID values.

```css
#special {
  color: red;
    }

h1#special {
  color: red;
    }
```

### Example:

#### Targeting ID attributes

In this example I want to target specific ID attribute values. Note how the styling is applied regardless of element type. ID selectors are extremely specific, and will overwrite most selector types.

#### Using ID selectors
Many designers avoid using ID selectors and discourage their use in projects due to their highly specific nature. ID selector styling is very hard to overwrite later, and generic interface styling can fail if dropped into a region being controlled through ID selectors. Still, ID selectors can play an important role in styling sites. You simply need to develop clear rules for when they are appropriate to use and how they might impact future styles.


## 04. Descendent Selectors

Descendent selectors allow you to take advantage of the natural structure of HTML documents by targeting elements based on the relationship between child and ancestor tags. These selectors are essential a combination of multiple selectors that are strung together to indicate structure. The descendent selector div p, for example, would match any paragraph found inside a div element. It’s important to note that the matching isn’t restricted to direct children. The example given would match any paragraph inside a div, no matter how many other elements the paragraph may be nested in.

### Syntax

Descendent selectors are created using a whitespace-separated string of selectors. Any selector type may be used in descendent selectors. The leftmost selector indicates a parent element followed by subsequent child elements. Each selector to the left of a selector is considered a parent, so in the case of article p span the selector would match any span element found within a paragraph that itself has an article tag as an ancestor. While there is no limit to the amount of selectors that can be used to create descendent selectors, any amount over three is generally considered to be inefficient.

```css
div p {
  color: red;
    }

.summary p span.warning {
  color: red;
    }
```

### Example:

#### Targeting nested elements
Descendent selectors allow us to be much more precise in terms of where styling is applied. Using them allows us to style elements a certain way when found inside a specific element type and another way if found elsewhere. This allows us to create discreet areas of styling in an efficient manner. It also makes it easy to create self-contained elements, as class and ID attributes can be used to identify specific UI elements that are styled with a combination of descendent selectors.

#### Strategies for Descendent Selectors
Because descendent selectors are tied directly to the structure of your HTML, it’s difficult to plan any effective strategy for using them without first understanding how your site’s content will be structured. The main focus of any strategy outlining the use of descendent selectors should be to strike a balance between specificity and modularity. You want your selectors to properly style the targeted area, but not to the detriment of adding styles later that may need to overwrite these base styles.

## 05. Universal Selector

Matches all element types in the current document. While sometimes referred to as the ”wildcard” selector, this term is not entirely accurate. The universal selector matches all element types, regardless of structure. While useful, care must be taken when using the universal selector in that it can unintentionally overwrite inheritance in styles, and it can negatively impact browser performance if overused.

### Syntax

To write a universal selector simply use the asterisk (*) character. It can be combined with other selectors in descendent selectors as well.

```css
* {
  color: red;
    }

div * em {
  color: red;
    }
```

### Example:

Universal selectors are typically used to quickly apply global default values to all elements, such as a quick CSS reset or box-sizing properties. They can be combined with other selectors for specific targeting purposes as well.

## 06. Grouping Selectors

To create more efficient stylesheets, you can group selectors together that share the same formatting using a comma-separated list of selectors. If, for example, all of your headings were the same font and color, you could create a single grouped selector to style them rather than six individual selectors. Any selector type can be grouped together, and there is no limit to the amount of selectors that can be grouped together.

### Syntax

Selectors are grouped together by writing a comma-separated list of selectors, followed by a normal rule declaration block. The order that the selectors appear in does not matter, except for your own organization. Each selector in the group has its own specificity and is treated as a separate selector in the cascade.

```css
h1, h2, h3, .warning, div em {
  color: red;
    }
```
