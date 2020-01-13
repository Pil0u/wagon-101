# HTML 101

This page was written following [CodeCademy Introduction to HTML](https://www.codecademy.com/learn/learn-html/) and Le Wagon's additional resources.

* [The basics](#the-basics)
* [Forms](#forms)
* [Semantic HTML](#semantic-html)


The basics
----------

Vocabulary: `<tag attributeName="attributeValue">content</tag>`

> It’s best to use a `<span>` element when you want to target a specific piece of content that is in-line, or on the same line as other text.

The style of an HTML page will be handled with CSS. However, HTML has *italic* and **bold** tags, `<em>` (for emphasize) and `<strong>`.
Image syntax: `<img src="path_to_image" />`. The final `/` is optional. Use the `alt` attribute to describe the image (+ SEO).
Video syntax: `<video src="path_to_video" width="640" height="480" controls>Text when video is not supported</video>`.

[Codecademy cheatsheet](https://www.codecademy.com/learn/learn-html/modules/learn-html-elements/reference)

The anchor HTML element creates hyperlinks. Example: `<a href="https://www.codecademy.com">Codecademy</a>`.
You can use an HTML `id` as the `href` attribute.
The attribute `target="_blank"` could be added to make the browser open the link in a new tab.

Typical structure of a HTML file:

``` html
<!DOCTYPE html>
<html>
  <head>
    <title>Title of the HTML page</title>
    <!-- metadata, "brain" of the page -->
  </head>
  <body>
    <!-- actual content of the page -->
  </body>
</html>
```

A table structure that encapsulates most of the underlying concepts:

``` html
<table>
  <thead>
    <tr>
      <th></th>
      <th>Male</th>
      <th>Female</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Life Expectancy</th>
      <td>78</td>
      <td>81</td>
    </tr>
    <tr>
      <th>Is alien?</th>
      <td colspan="2">No</td>
    </tr>
    <tr>
      <th>Smokers rate</th>
      <td rowspan="2">18</td>
      <td>23</td>
    </tr>
    <tr>
      <th>Alcoholic rate</th>
      <td>14</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th>Footer</th>
      <td>Equal</td>
      <td>Equal</td>
    </tr>
  </tfoot>
</table>
```

Forms
-----

Raw form with major input types:

``` html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Forms Review</title>
  </head>
  <body>
    <section id="overlay">
      <img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">
      <hr>
      <form action="submission.html" method="POST">
				<h1>Create a burger!</h1>
        <section class="protein">
          <label for="patty">What type of protein would you like?</label>
    			<input type="text" name="patty" id="patty">
        </section>
        <hr>

        <section class="patties">
          <label for="amount">How many patties would you like?</label>
          <input type="number" name="amount" id="amount">
        </section>
        <hr>

        <section class="cooked">
          <label for="doneness">How do you want your patty cooked</label>
          <br>
          <span>Rare</span>
          <input type="range" name="doneness" id="doneness" value="3" min="1" max="5">
          <span>Well-Done</span>
        </section>
        <hr>

        <section class="toppings">
          <span>What toppings would you like?</span>
          <br>
          <input type="checkbox" name="topping" id="lettuce" value="lettuce">
          <label for="lettuce">Lettuce</label>
          <input type="checkbox" name="topping" id="tomato" value="tomato">
          <label for="tomato">Tomato</label>
          <input type="checkbox" name="topping" id="onion" value="onion">
          <label for="onion">Onion</label>
        </section>
        <hr>

        <section class="cheesy">
          <span>Would you like to add cheese?</span>
          <br>
          <input type="radio" name="cheese" id="yes" value="yes">
          <label for="yes">Yes</label>
          <input type="radio" name="cheese" id="no" value="yes">
          <label for="no">No</label>
        </section>
        <hr>

        <section class="bun-type">
          <label for="bun">What type of bun would you like?</label>
          <select name="bun" id="bun">
            <option value="sesame">Sesame</option>
            <option value="potatoe">Potato</option>
            <option value="pretzel">Pretzel</option>
          </select>
        </section>
        <hr>

        <section class="sauce-selection">
          <label for="sauce">What type of sauce would you like?</label>
          <input list="sauces" id="sauce" name="sauce">
          <datalist id="sauces">
            <option value="ketchup"></option>
            <option value="mayo"></option>
            <option value="mustard"></option>
          </datalist>
        </section>
        <hr>
        <section class="extra-info">
          <label for="extra">Anything else you want to add?</label>
          <br>
          <textarea id="extra" name="extra" rows="3" cols="40"></textarea>
        </section>
        <hr>

        <section class="submission">
          <input type="submit" value="Submit">
        </section>
      </form>
    </section>
  </body>
</html>
```

Form validations are executed client side (before the form is sent). Some attributes:
* `required` for mandatory element
* `min` and `max` for numeric input (i.e. number, range)
* `minlength` and `maxlength` for text input (i.e. text, textarea, password)
* `pattern` for regular expressions

Semantic HTML
-------------

Semantic HTML provides context within the structure of the HTML page:
* with structural tags like `<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<aside>`
* with media integration tags like `<figure>` and its `<figcaption>`, `<video>`, `<embed>` and `<audio>`
* Notes: within `<figure>` you add an `<img src="">` tag, within `<audio>` you add a `<source src="">` tag but `<video>` and `<embed>` already have their own `src` tag. Don't forget to add controls in `<audio>` and `<video>`!
