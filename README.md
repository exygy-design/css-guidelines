# HTML and CSS Guidelines
Best practices and guidelines for writing HTML and CSS

## HTML

### Lean markup
Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML. For example:

```html
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```

## CSS

### Spacing
* Use soft-tabs with a two space indent. Spaces are the only way to guarantee code renders the same in any person’s environment.
* Use one space between property and value: width: 20px not width:20px.
* Put spaces before { in rule declarations.
* Put line breaks between rulesets.
* When grouping selectors, keep individual selectors to a single line.
* Place closing braces of declaration blocks on a new line.
* Each declaration should appear on its own line for more accurate error reporting.

### Formatting
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

### Order
* Use alphabetical order for declarations.
* Place @extends and @includes at the top of your declaration list.
* Place media queries directly after the declaration list.
* Place concatenated selectors second.
* Place pseudo-states and pseudo-elements third.
* Place nested elements fourth.
* Place nested classes fifth.

### Selectors
* Don't use ID's for style.
* Use meaningful names: $visual-grid-color not $color or $vslgrd-clr.
* Use ID and class names that are as short as possible but as long as necessary.
* Avoid using the direct descendant selector >.
* Avoid nesting more than 3 selectors deep.
* Use HTML tags on vague classes that need a qualifier like header.application not .main.
* Avoid using the HTML tag in the class name: section.news not section.news-section.
* Avoid using HTML tags on classes for generic markup <div>, <span>: .widgets not div.widgets.
* Avoid using comma delimited selectors.
* Avoid nesting within a media query.

## Architecture
Split the scss codebase into meaningful separated folders so it is easy to find stuff later when you have to come back to the code.

```
sass/
|
|– base/
|   |– _reset.scss       # Reset/normalize
|   |– _typography.scss  # Typography rules
|   …                    # Etc.
|
|– components/
|   |– _buttons.scss     # Buttons
|   |– _carousel.scss    # Carousel
|   |– _cover.scss       # Cover
|   |– _dropdown.scss    # Dropdown
|   …                    # Etc.
|
|– layout/
|   |– _navigation.scss  # Navigation
|   |– _grid.scss        # Grid system
|   |– _header.scss      # Header
|   |– _footer.scss      # Footer
|   |– _sidebar.scss     # Sidebar
|   |– _forms.scss       # Forms
|   …                    # Etc.
|
|– pages/
|   |– _home.scss        # Home specific styles
|   |– _contact.scss     # Contact specific styles
|   …                    # Etc.
|
|– utils/
|   |– _variables.scss   # Sass Variables
|   |– _functions.scss   # Sass Functions
|   |– _mixins.scss      # Sass Mixins
|   |– _helpers.scss     # Class & placeholders helpers
|
|– vendors/
|   |– _bootstrap.scss   # Bootstrap
|   |– _jquery-ui.scss   # jQuery UI
|   …                    # Etc.
|
|
`– main.scss             # Main Sass file
```

```scss
@import 'utils/variables';
@import 'utils/functions';
@import 'utils/mixins';
@import 'utils/placeholders';

@import 'vendors/bootstrap';
@import 'vendors/jquery-ui';

@import 'base/reset';
@import 'base/typography';

@import 'layout/navigation';
@import 'layout/grid';
@import 'layout/header';
@import 'layout/footer';
@import 'layout/sidebar';
@import 'layout/forms';

@import 'components/buttons';
@import 'components/carousel';
@import 'components/cover';
@import 'components/dropdown';

@import 'pages/home';
@import 'pages/contact';

@import 'themes/theme';
@import 'themes/admin';
```

## References
* https://github.com/thoughtbot/guides
* http://primercss.io/guidelines/
* http://sass-guidelin.es/#architecture

