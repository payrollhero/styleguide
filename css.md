## CSS Styleguide

*A reasonable style guide for modern CSS development.*

## <a name='TOC'>Table of Contents</a>

1. [Whitespace](#whitespace)
1. [Formatting](#formatting)
1. [Declaration Order](#declaration-order)
1. [Naming Conventions](#naming-conventions)
1. [Comments](#comments)
1. [Resources](#resources)

## <a name='whitespace'>Whitespace</a>

Use soft tabs set to 2 spaces.

```css
/* Bad */
.selector {
....display: block;
}

/* Good */
.selector {
..display: block;
}
```

Place 1 space before the leading brace and place 1 space after the colon of a declaration.

```css
/* Bad */
.selector{
  float:left;
}

/* Good */
.selector {
  float: left;
}
```

Place an empty newline at the end of the file.

```css
/* Bad */
.selector {
  clear: both;
}
```

```css
/* Good */
.selector {
  clear: both;
}

```

**[[⬆]](#TOC)**

## <a name='formatting'>Formatting</a>

The chosen code format ensures that code is: easy to read; easy to clearly comment; minimises the chance of accidentally introducing errors; and results in useful diffs and blames.

+ Use 1 selector per line in multi-selector rulesets
+ Use 1 declaration per line in a declaration block
+ Use lowercase and shorthand hex values
+ Use double quotes `""` e.g. `input[type="checkbox"]`
+ *Where allowed*, avoid specifying units for zero-values e.g. `margin: 0`
+ Include a space after each comma in comma-separated property or function values
+ Include a semi-colon at the end of the last declaration in a declaration block
+ Place the closing brace of a ruleset in the same column as the first character of the ruleset
+ Separate each ruleset by a blank line

```css
/* Bad */
.selector-1, .selector-2, .selector-3 { display: block; font-family: helvetica,arial,sans-serif; background: #fff; background: linear-gradient(#fff,rgba(0,0,0,.8)) }
.selector-a, .selector-b { padding: 10px }

/* Good */
.selector-1,
.selector-2,
.selector-3 {
  display: block;
  font-family: helvetica, arial, sans-serif;
  background: #fff;
  background: linear-gradient(#fff, rgba(0, 0, 0, 0.8));
}

.selector-a,
.selector-b {
  padding: 10px;
}
```

**[[⬆]](#TOC)**

## <a name='naming-conventions'>Naming Conventions & Class vs ID</a>

+ **Only** Use IDs for things that are unique
+ **Only** Use IDs for javascript control, not styling
+ **Good** Use separate classes for control versus look & feel.
+ **Bad** Combining class name look & feel with control flow.

Use meaningful classnames for control flow in HAML and meaningful look & feel names in css.


HAML
```haml
/good
#page-notice
  .when-error.error-notice
    /error data goes here
  .when-warning.warning-notice
  
/bad
#page-notice
  #when-error
    /data
  #when-warning
```

CSS
```css
/* Good */
#page-notice {
  float: left;
}

.error-notice {
  color: red;
}

.warning-notice {
  color: yellow;
}

/* Bad */
#page-notice {
  float: left;
  
  #when_error {
    color: red;
  }
  
  #when-warning {
    color: yellow;
  }
  
}


```

Use ID and class names that are as short as possible but as long as necessary.

```css
/* Bad */
#navigation {
  display: block;
}

.atr {
  font-weight: bold;
}

/* Good */
.nav {
  display: block;
}

.author {
  font-weight: bold;
}
```

Separate words in ID and class names with a hyphen.

```css
/* Bad */
.demoimage {
  border: 1px solid #ccc;
}

.error_text {
  color: #f00;
}

/* Good */
.demo-image {
  border: 1px solid #ccc;
}

.error-text {
  color: #f00;
}
```

Avoid qualifying ID and class names with type selectors.

```css
/* Bad */
ul#example {
  list-style: none;
}

div.error-block {
  background: #fff0f0;
}

/* Good */
#example {
  list-style: none;
}

.error-block {
  background: #fff0f0;
}
```

All code should be lowercase: This applies to element names, attributes, attribute values, selectors, properties and property values.

```css
/* Bad */
BODY {
  margin: 0;
}

/* Good */
body {
  margin: 0;
}
```

**[[⬆]](#TOC)**

## <a name='styling_areas'>Styling Entire Areas</a>
Our general principle for styling entire areas in custom ways is to use our existing styles to style the page.  Then use new classes which contain the entire set of elements upon which you apply specific styling.

Example.
HAML
```haml
.my-clock-container
  %button.success-button
    Clock In!
    
  %ul.float-right.clock-in-photos
    %li My Clockin
```

SCSS
```scss
.my-clock-container {
  width: 500px;
  
  .success-button {
    font-size: 150%;
  }
  
  ul.clock-in-photos {
    list-style: none;
  }
}

```

+ We **aim** to have as many generic style elements as possible which define our overall style.
+ We **always** use a containing element under which we define the styling for an area.
+ We **aim** to break more generic style elements into our style guide and into the general.css file

## <a name='comments'>Comments</a>

```css
/* ==========================================================================
   Section comment block
   ========================================================================== */

/* Sub-section comment block
   ===================================== */

/**
 * This is a docBlock style comment
 *
 * This is a longer description of the comment, describing the code in more
 * detail. Limit these lines to a maximum of 80 characters in length.
 */

/* Basic comment */
```

**Example**:

```css
/* ==========================================================================
   Typography
   ========================================================================== */

p {
  margin: 0 0 20px;
  font-size: 16px;
}

/* Headings
   ===================================== */

h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0 0 20px;
  font-family: serif;
  font-weight: bold;
  text-rendering: optimizelegibility; /* Fix the character spacing for headings */
}
```

### Above all else

Follow your :heart:

**[[⬆]](#TOC)**

## <a name='resources'>Resources</a>

**Blogs**

+ [CSS-Tricks](http://css-tricks.com/)

**Other Styleguides**

+ [GitHub CSS Style Guide](https://github.com/styleguide/css)
+ [CSS Guidelines (csswizardry)](https://github.com/csswizardry/CSS-Guidelines)
+ [Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
+ [Principles of Writing Consistent, Idiomatic CSS](https://github.com/necolas/idiomatic-css)
+ [Isobar Front-end Code Standards & Best Practices](http://isobar-idev.github.com/code-standards/#_css)

**[[⬆]](#TOC)**
