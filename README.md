# css-guidelines
Best practices and guidelines for writing HTML and CSS

## Spacing
* Use soft-tabs with a two space indent. Spaces are the only way to guarantee code renders the same in any person’s environment.
* Use one space between property and value: width: 20px not width:20px.
* Put spaces before { in rule declarations.
* Put line breaks between rulesets.
* When grouping selectors, keep individual selectors to a single line.
* Place closing braces of declaration blocks on a new line.
* Each declaration should appear on its own line for more accurate error reporting.

## Formatting
* Use the SCSS syntax.
* Use hyphens when naming mixins, extends, classes, functions & variables: span-columns not spanColumns.
* Prefer hex color codes #fff or #FFF.
* Avoid using shorthand properties for only one value: background-color: #ff0000;, not background: #ff0000;
* Use // for comment blocks not /* */.
* Use one space between selector and {.
* Use double quotation marks.
* Use only lowercase, except for hex or string values.
* Don't add a unit specification after 0 values, unless required by a mixin.
* Use a leading zero in decimal numbers: 0.5 not .5
* Use double colons for pseudo-elements.

