# CSS

This page was written following [CodeCademy Learn CSS](https://www.codecademy.com/learn/learn-css/) and Le Wagon's additional resources.

Vocabulary:

``` css
selector {
	attribute: value;
}
```

*Specificity* is how the browser prioritize styling rules, by selector type: `#id` > `.class` > `<tag>`

> To make styles easy to edit, it’s best to style with a tag selector, if possible. If not, add a class selector. If that is not specific enough, then consider using an ID selector.

Chaining clarification:
* with `p.classname {...}`, you are looking for every `<p>` tag stamped with the class `classname`
* with `.classname p {...}`, you are looking for every `<p>` tag that is nested in/a descendant of any tag with the class `classname`
* 
