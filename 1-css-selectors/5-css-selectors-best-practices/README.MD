## 01. Writing efficient selectors

Writing efficient selectors goes far beyond just using the shortest selector possible. The selectors in your stylesheets work together to form a cohesive whole, and without a guiding strategy you’ll end up using more selectors than you need and in a form that doesn’t reflect the goals of your project. Authoring selectors should be guided more by the organizational goals of the site than by any perceived performance optimization strategy. While you should always strive to write the most efficient selectors possible, it’s far more important to author styles that are easy to maintain and extend

### Use Inheritance

Rather than defining the same property multiple times, take advantage of inheritance to pass properties down to child elements. This will result in fewer selectors and more efficient styles.

```css
Unnecessary rules
h1 { font-family: "Arial"; }
h2 { font-family: "Arial"; }
h3 { font-family: "Arial"; }
p { font-family: "Arial"; }

Using inheritance
body { font-family: "Arial"; }
```

### Group When Possible

If there are multiple rules that share styling, group them together into a single rule. This will reduce code bloat and make it easier to update styles.

```css
Multiple rules
h1 {color: red; font-weight: normal;}
h2 { color: red; font-weight: normal;}
h3 { color: red; font-weight: normal;}
Grouped
h1, h2, h3  {color: red; font-weight: normal;}
```

### Reduce Depth

Longer descendent selectors are more expensive to parse, and result in styles that are too closely tied to a specific structure. Keeping selectors as short as possible without causing styling conflicts should be the goal of every stylesheet.

```css
Unnecessarily descriptive
main article.support p em {
  color: red;
    }
Sufficient depth
.support em {
  color: red;
    }
```

### Modularize With Classes

If you need to reuse styles, have multiple authors, or if the project is a large site with a high degree of maintenance and content updates consider modularizing styles with classes. For example if you have a search feature built in, don’t rely on the structure of the page alone to write the selectors. Consider using a class which can be reused on other projects or injected into other regions of the site without needing additional styling.

```css
Tied to page structure
nav aside input[type="search"] {
  ...
    }
Modularized
.search input {
  ...
    }
```
