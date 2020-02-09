# CSS 101

This page was written following [CodeCademy Learn CSS](https://www.codecademy.com/learn/learn-css/) and Le Wagon's additional resources.

## Basics

This is a *rule set*:

``` css
selector {
	property: value;
}
```

*Specificity* is how the browser prioritize styling rules, by selector type: `#id` > `.class` > `<tag>`

> To make styles easy to edit, it’s best to style with a tag selector, if possible. If not, add a class selector. If that is not specific enough, then consider using an ID selector.

Chaining clarification:
* with `p.classname {...}`, you are looking for every `<p>` tag stamped with the class `classname`
* with `.classname p {...}`, you are looking for every `<p>` tag that is nested in/a descendant of any tag with the class `classname`

Separate CSS selectors with commas to apply one rule for multiple selectors.

## Box-models and positioning

<img src="https://s3.amazonaws.com/codecademy-content/courses/freelance-1/unit-4/diagram-boxmodel.svg" alt="The Box Model" width="540">

`margin` and `padding` syntaxes:
* `top right bottom left` (in pixels)
* `top_bottom left_right` (in pixels)
* to centre using `0 auto`, you need to specify a `width`

Horizontal margins add up, vertical margins overlap:
<img src="https://s3.amazonaws.com/codecademy-content/courses/freelance-1/unit-4/diagram-verticalmargins.svg" alt="Effective margin distances" width="540">

`overflow` can be set to `display`, `hide` or `scroll`.

> An element with `display: none` will be completely removed from the web page. An element with `visibility: hidden`, however, will not be visible on the web page, but the space reserved for it will.

<img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/htmlcss1-diagram__contentbox.svg" alt="The Content-Box Model" width="540">
vs
<img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/htmlcss1-diagram__borderbox.svg" alt="The Border-Box Model" width="540">

that can be triggered with:
``` css
* {
  box-sizing: border-box;
}
```

By default, elements have a `position` property set to `static`.
* `relative` positions an element relative to its default static position on the web page
* `absolute` positions an element relative to its closest positioned parent element
* `fixed` fixes an element to a specific position on the page, regardless of user scrolling

Use the `z-index` property (integers) to manage elements overlapping.

`strong` or `em` tags are `display: inline` by default, i.e. matches exactly to the content size.
`headings`, `p` and `div` are `display: block` by default, i.e. fills the entire width and matches height to the content.
`display: inline-block` combines both of them, allowing divs to align horizontally while keeping content as blocks.

## Fonts

**Not more than 3 different fonts for one page.**

Main properties are `font-family`, `font-weight`, `text-align` (center)  
Other interesting properties: `font-style` (normal, _italic_), `word-spacing` (0.25em), `letter-spacing` (0.3em), `text-transform` (uppercase), `line-height` (1.4)

Using external fonts is possible with Google Font or `@font-face`.  
We can also host our own fonts and call them locally with `@font-face`:
``` css
@font-face {
  font-family: "Roboto";
  src: url(fonts/Roboto.woff2) format('woff2'), /* lightweight format */ 
       url(fonts/Roboto.woff) format('woff'),
       url(fonts/Roboto.tff) format('truetype');
}
```

Resources to find fonts:
* [Font Squirrel](https://www.fontsquirrel.com/)
* [GetTheFont](https://www.getthefont.com/)

## CSS Grids

### Basics

Keyword: `display: grid;`  
`grid-template: 40px 50px / 100%;` is the equivalent of `grid-template-rows: 40px 50px; grid-template-columns: 100%;`  
You can use the `repeat()` function, useful to build a equally sized grid with `fr`: `grid-template: repeat(3, 1fr) / repeat(5, 1fr);`  
You can use the `minmax(min, max)` function with a responsive grid, to set size boundaries of columns or rows.  
`grid-gap: 20px 10px` to set the distance between rows to 20 pixels and the distance between columns to 10 pixels.

<img src="https://s3.amazonaws.com/codecademy-content/courses/learn-css-grid/lesson-i/css_grid_diagram_2.svg" alt="Grid and grid items" width="540">

`grid-row: 1 / 3;` ~ `grid-row-start: 1; grid-row-end: 3;` (matches the A example above)  
`grid-column: 4 / 6;` ~ `grid-column: 4 / span 2;`  
`grid-area: grid-row-start / grid-column-start / grid-row-end / grid-column-end`  

### Advanced

`grid-template-areas` helps naming elements to cover specific areas of the grid. Each element needs a name specified in a `grid-area` property.  
`justify-items` positions elements of the grid on the row axis. `justify-content` positions groups of elements.  
Respectively for the column axis: `align-items` and `align-content`.  
Use `justify-self` or `align-self` to override for a specific element.

`grid-auto-rows` specifies the height of rows added implicitly to the grid.  
`grid-auto-columns` specifies the width of columns added implicitly to the grid.  
`grid-auto-flow` specifies in which direction implicit elements should be created.  
