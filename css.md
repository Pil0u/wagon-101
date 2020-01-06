# CSS 101

This page was written following [CodeCademy Learn CSS](https://www.codecademy.com/learn/learn-css/) and Le Wagon's additional resources.

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

Fonts: not more than 3 different fonts for one page.

![The Box Model](https://s3.amazonaws.com/codecademy-content/courses/freelance-1/unit-4/diagram-boxmodel.svg "The Box Model")

`margin` and `padding` syntaxes:
* `top right bottom left` (in pixels)
* `top_bottom left_right` (in pixels)
* to centre using `0 auto`, you need to specify a `width`

Horizontal margins add up, vertical margins overlap:
![Effective margin distances](https://s3.amazonaws.com/codecademy-content/courses/freelance-1/unit-4/diagram-verticalmargins.svg "Effective margin distances")

`overflow` can be set to `display`, `hide` or `scroll`.

> An element with `display: none` will be completely removed from the web page. An element with `visibility: hidden`, however, will not be visible on the web page, but the space reserved for it will.
