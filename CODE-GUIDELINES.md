# PatternFly 5 HTML/CSS Code Guidelines

Please enforce these guidelines at all times. Small or large, call out what's incorrect.

Every line of code should appear to be written by a single person, no matter the number of contributors.

This set of rules generate some constraints and conventions. If you run into instances where a convention isn’t obvious or a solution could be handled in a few different ways, contact the PatternFly community, have a conversation about how to handle it and update this guidelines when needed.


## Table of content

- [Harry Robert's Guidelines](#harry-robert-s-guidelines)
  - [Exceptions](#exceptions)
  - [Deviations](#deviations)
    - [HTML](#html)
    - [Lintable HTML rules](#lintable-html-rules)
    - [Comment and Organization](#comment-and-organization)
  - [Additions](#additions)
    - [Lintable CSS rules](#lintable-css-rules)
    - [Shorthand notation](#shorthand-notation)
    - [Typography](#typography)
    - [Spaces, margins and padding](#spaces--margins-and-padding)
    - [Shadows](#shadows)
    - [Gradients](#gradients)
  - [Sass](#sass)
    - [Nesting](#nesting)
    - [Variables](#variables)
    - [Mixins](#mixins)
    - [@extend](#-extend)
- [How to write PatternFly selectors](#how-to-write-patternfly-selectors)
  - [Namespace](#namespace)
  - [Separation of UI structure concerns](#separation-of-ui-structure-concerns)
    - [Layout](#layout)
    - [Components](#components)
    - [Utilities](#utilities)
    - [Bootstrap components](#bootstrap-components)
- [Credits and references](#credits-and-references)


## Harry Robert's Guidelines

PatternFly follows [Harry Robert's CSS Guidelines](https://cssguidelin.es/) with some exceptions, deviations and additions.

### Exceptions

PatternFly doesn't follow these rules:

- [Table of contents](https://cssguidelin.es/#able-of-contents)
- [Titling](https://cssguidelin.es/#titling)
- [Anatomy of a Ruleset](https://cssguidelin.es/#anatomy-of-a-ruleset)
- [Multi-line CSS](https://cssguidelin.es/#multi-line-css)
- [Indenting](https://cssguidelin.es/#indenting)
- [Meaningful Whitespace](https://cssguidelin.es/#meaningful-whitespace)

### Deviations

#### HTML

**Practicality over purity**. Strive to maintain HTML standards and semantics, but not at the expense of practicality. Use the least amount of markup with the fewest intricacies whenever possible.

The CSS linter is PatternFly's single source of truth for CSS syntax, declaration order and other CSS rules like disallow type selectors, disallow vendor prefixes, and more.

#### Lintable HTML rules

The HTML linter is PatternFly's single source of truth for HTML syntax, Attribute order and other HTML rules.


#### Comment and Organization

Code is written and maintained by people. Ensure your code is descriptive, well commented, and approachable by others. Great code comments convey context or purpose. Do not simply reiterate a component or class name.

Be sure to write in complete sentences for larger comments and succinct phrases for general notes.

Follow this comment structure:

1. License header
1. Doc Block
1. Sections
1. Line


```sass
/**
* Copyright 2016 Red Hat, Inc
* Licensed under the Apache License, Version 2.0 (the "License");
* you may not use this file except in compliance with the License.
* You may obtain a copy of the License at
*
*     http://www.apache.org/licenses/LICENSE-2.0
*
* Unless required by applicable law or agreed to in writing, software
* distributed under the License is distributed on an "AS IS" BASIS,
* WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
* See the License for the specific language governing permissions and
* limitations under the License.
*/



//
// Component heading
// --------------------------------------------------
//  Sometimes you need to include optional context for the entire component. Do that up here if it's important enough.


// Section level Comment
.selector {
  line-height: 1.5; // Line level Comment
  color: #333;
}
```

##### 1. License header

PatternFly is license under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

- Always add the Apache v2.0 license header at the top of each scss files.
- Leave three blank lines bellow.

##### 2. Doc Block

- Includes the name of the component and an optional comment.
- Leave two blank lines bellow.

##### 3. Section

This comment is a section divider or describes a block of code.

- Leave one blank lines above.

##### 4. Line

Describes a specific line of code.


### Additions

#### Lintable CSS rules

The CSS linter is PatternFly's single source of truth for CSS syntax, declaration order and other CSS rules like disallow type selectors, disallow vendor prefixes, and more.

#### Shorthand notation

Limit the use of shorthand declarations to instances where you must explicitly set all the available values. Common overused shorthand properties include:

- `padding`
- `margin`
- `font`
- `background`
- `border`
- `border-radius`

```sass
// Bad
.element {
  margin: 0 0 10px;
  background: red;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}

// Good
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```

The [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties) and [Harry Robert](https://csswizardry.com/2016/12/css-shorthand-syntax-considered-an-anti-pattern/) both have great articles on shorthand properties for those unfamiliar with notation and behaviour.


#### Typography

Every typography element has a zero margin and base `font-size`. Margins and font treatments are added with classes.

```html
<h1 class="pf-h1">Heading</h1>
<h2 class="pf-h2">Heading</h2>
<h3 class="pf-h3">Heading</h3>
<h4 class="pf-h4">Heading</h4>
<h5 class="pf-h5">Heading</h5>
<h6 class="pf-h6">Heading</h6>
```

The opt-in class `.pf-vertical-rythm` restores vertical rythm and heading font size.

```html
<div class="pf-vertical-rythm">

  <h1>Main title</h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
  <p>Excepteur sint occaecat cupidatat non proident, sunt in</p>

  <h2>Secondary title</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
  <p>Excepteur sint occaecat cupidatat non proident, sunt in</p>

</div>
```

#### Spaces, margins and padding

PatternFly has a set of spacer variables:

```sass
$pf-spacer-xxxs
$pf-spacer-xxs
$pf-spacer-xs
$pf-spacer-sm
$pf-spacer-md
$pf-spacer-lg
$pf-spacer-xl
$pf-spacer-xxl
$pf-spacer-xxxl
$pf-spacer-xxxxl
```

Always use them to define `margin` and `padding`

```sass
.nav-link {
  padding-bottom: $pf-spacer-xxxs;
}

.dropdown-menu {
  margin-left: $pf-spacer-sm;
}
```

You can also use [Bootstrap spacing utilities](http://v4-alpha.getbootstrap.com/utilities/spacing/) with PatternFly sizes:

```html
<p class="mb-lg">This paragraph has a large bottom margin</p>
```

##### Comment all magic numbers

If a situation arises where a value needs entering into the authoring style sheets that isn't already defined in the variables this should serve as a red flag to you.

In the case where a 'magic' number needs entering in the authoring style sheets, ensure a comment is added on the line above to explain its relevance.


#### Shadows

PatternFly has 6 types of shadows:

```sass
$pf-box-shadow-sm
$pf-box-shadow-md
$pf-box-shadow-lg
$pf-box-shadow-inset
$pf-box-shadow-left
$pf-box-shadow-right
```

Always use variables to apply `box-shadow`:

```sass
.btn {
  box-shadow: $pf-box-shadow-sm;
}
```

You can also use box shadow utilities to add or remove shadows to any element:

```html
<p class="pf-box-shadow-md">This paragraph has a medium box shadow</p>

<button class="btn btn-primary pf-box-shadow-none">This button has no shadow</button>
```

#### Gradients
PatternFly has one slight gradient to define panel headers, table headers, secondary btns and other elements. Always use the PatternFly gradient mixin to define it.

```sass
thead th {
  @include pf-gradient;
}
```

### Sass

PatternFly uses [Sass](http://sass-lang.com/) to preprocess CSS.

As a general rule don't overcomplicate Sass, keep it easy to parse for a normal human.

#### Nesting

Avoid Sass nesting, if absolutely necessary, don't exceed a three layer depth.

Limit nesting to the following use cases:

1. Modifiers of a style block
1. Media queries
1. Context selectors
1. States, pseudo-classes and pseudo-elements

Use the least number of selectors required to style an element. As a rule, if a selector will work without it being nested then do not nest it.

##### 1. Modifiers of a style block

Make use of [Sass’s parent selector](https://css-tricks.com/the-sass-ampersand/ mechanism to write BEM elements and modifiers, you should only have one block selector:

```sass
// Good
.pf-nav {

  &_item {
    ...
  }

  &--modifier {
    ...
  }
}

// Bad
.pf-nav {
  ...
}

.pf-nav--modifier {
  ...
}

.pf-nav_item {
  ...
}
```


##### 2. Media queries

Component-specific media queries should be nested inside the component block. Use [Bootstrap responsive breakpoints mixins](http://v4-alpha.getbootstrap.com/layout/overview/#responsive-breakpoints) and remember that PatternFly is mobile first.

**Do progressive enhancement, not gracefully degradation.**


```sass
.pf-nav {
  ...

  // Styles for small view ports and up
  @include media-breakpoint-up(sm) { ... }
}
```

##### 3. Context selectors

Context selectors should be avoided. If a component is different due to it's location, then you should consider creating a new component.

But if you must declare a context selector make use of [Sass’s parent selector](https://css-tricks.com/the-sass-ampersand/ mechanism. This allows all rules for a given component to be maintained in one location.

```sass
.pf-nav {
  .pf-header & {
    ...
  }
}
```

All styles for `.pf-nav` should be found in one place, rather than scattered throughout multiple partial files.

##### 4. States, pseudo-classes and pseudo-elements

States of a component should be included as a nested element. This includes hover, focus, and active states:

```sass
.btn {
  background: $color;

  &:hover, &:focus {
    background: $lighter-color;
  }
}
```

#### Variables

Variable format follows the `$component-modifier-state-property` order.

Since PatternFly components are isolated, every value should have a component scoped variable, unless it's an intentional decision, then we hardcoded it.

```scss
$pf-secondary-nav-item-margin-left: $pf-spacer-sm !default;

.pf-secondary-nav__item  {
  margin-left: $pf-secondary-nav-item-margin;
  &:last-child {
    margin-right: 0;
  }
}
```

**Don't reinvent the wheel:** Always use variables for spaces, colors, shadows and typography treatment.


#### Mixins

The rule of thumb is that if you happen to spot a group of CSS properties that always appear together for a reason (i.e. not a coincidence), you can put them in a mixin instead.

Another valid example would be a mixin to size an element, defining both width and height at the same time. Not only would it make the code lighter to type, but also easier to read.

The keyword for using mixins is **simplicity**:

- Don't over-engineer
- Don’t over think your code
- above all keep it simple.

If a mixin ends up being longer than 20 lines or so, then it should be either split into smaller chunks or completely revised.

```sass
// Helper to size an element
// @param {Length} $width
// @param {Length} $height

@mixin size($width, $height: $width) {
  width: $width;
  height: $height;
}
```

#### @extend

Don't use `@extend`.

## How to write PatternFly selectors

Since PatternFly is based on Bootstrap, we follow some rules to keep our library isolated, easy to maintain and grow.

### Namespace

To avoid conflicts PatternFly prefixes all classes with “pf-”. This also helps differentiate PatternFly and Bootstrap class names.

```sass
// Bad
.selector {
  ...
}

// Good
.pf-selector {
  ...
}
```

### Separation of UI structure concerns

UI structures fall into 4 categories:

- Layouts
- Components
- Utilities
- Bootstrap components

#### Layout

Layout are containers concerned with the vertical and horizontal alignment and spacing of their children. The classes are prefixed with `-l` (after the patterfly prefix `pf-`), for example: `.pf-l-grid` or `.pf-l-list`.

#### Components

Components are modular and independent structures concerned with how a thing looks.

- A component always touches all four sides of its parent container. No element will have top or left margins and all last children (right or bottom) will have their margins cleared.
- The component itself never has widths or floats.
- Elements inside a component never use top margins. The first element touches the top of its component.

The parent container of a component is prefixed with `-c` (after the patterfly prefix `pf-`), for example: `.pf-c-masthead`.

##### When to create a new component?

As a general rule create extension to an element with BEM modifiers if it’s a change of color or scale, if the change generates a new entity, then create a new component.

Repetition is better than the wrong abstraction.


#### Utilities

Utility classes have the single purpose to reduce the frequency of highly repetitive declarations.

Utility classes are prefixed with `-u` for example `.pf-u-shadow-sm`.


#### Bootstrap components

Keep PatternFly styles independent from Bootstrap.

When writing a PatternFly component **don't extend or build on top of Bootstrap structure**.

**Follow these rules to style Bootstrap components:**

- Start by overwriting Bootstraps variables on `pf-variables.scss`
- If it needs further modifications, create a `pf-component.scss` and base your styles on the original bootstrap scss file.
- Be precise and accurate, introduce as little modifications as possible to achieve the desired result.
- Bootstrap uses a modified version of BEM: `{{block}}-{{element}}-{{modifier}}`.

```sass
// Overwrite Bootstrap card block
.card {
  border: none;
}

// Overwrite Bootstrap card header element
.card-header{
  background: $pf-card-cap-bg;
  border-bottom-color: $pf-card-border-color;
}

// Overwrite Bootstrap card footer element
.card-footer{
  background: $pf-card-footer-bg;
  border-top-color: $pf-card-border-color
}

// Introduces PatternFly card modifier
.pf-card--accented {
  border-top: 2px solid $pf-color-blue-300;
}
```


## Credits and references

This guide is inspired by people we follow and respect:

- **[Mark Otto](http://markdotto.com/):** [Code Guideline](http://codeguide.co/)
- **[Robert Harris](http://csswizardry.com/):** [CSS Guidelines](http://cssguidelin.es/)
- **[Gravity Department](http://gravitydept.com/)**: [Style Guide Field Manual](http://manuals.gravitydept.com/code/css/style-guide)
- **[Hugo Giraudel](http://hugogiraudel.com/):** [SASS Guidelines](https://sass-guidelin.es/)

Thank you :heart:
