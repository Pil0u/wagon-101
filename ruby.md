# Ruby 101

This page was written following Le Wagon's internal resources.

## Official Ruby doc (2.6.5)

### Basic classes
* [Array](https://ruby-doc.org/core-2.6.5/Array.html)
* [Enumerable](https://ruby-doc.org/core-2.6.5/Enumerable.html)
* [Integer](https://ruby-doc.org/core-2.6.5/Integer.html)
* [Float](https://ruby-doc.org/core-2.6.5/Float.html)
* [String](https://ruby-doc.org/core-2.6.5/String.html)
* [Symbol](https://ruby-doc.org/core-2.6.5/Symbol.html)

### Utilities
* [Exception](https://ruby-doc.org/core-2.6.5/Exception.html)
* [File](https://ruby-doc.org/core-2.6.5/File.html)
* [IO](https://ruby-doc.org/core-2.6.5/IO.html)
* [Random](https://ruby-doc.org/core-2.6.5/Random.html)
* [Regexp](https://ruby-doc.org/core-2.6.5/Regexp.html)
* [Time](https://ruby-doc.org/core-2.6.5/Time.html)

## Core Ruby

* `%w(item1, item2)` ~ `["item1", "item2"]`
* `p <object>` ~ `puts <object>.inspect`
* `Symbol` ~ Immutable `String`, with storage optimization. Syntax: `:symbol`
* Converting binary: `"%032b" % number` ~ `number.to_s(2).rjust(32, '0')`
* On a `RegExp` object with groups `()`, use the `.match` method with a `String` as parameter
* Use the `.scan` method to retrieve all matches in an `Array`
* When dividing numbers, add a `.to_f` to one of them if you want floating point results
* Casting elements of an `Array`: `an_array.map(&:to_i)`
* Copying an object: `my_object.clone`
* Console parameters are stored in a `ARGV` Array
* Sorting a Hash by values: `my_hash.sort_by { |_key, value| value }`


### Basic scraping with `Nokogiri`

``` ruby
doc = Nokogiri::HTML(open("https://myurl.com"), nil, 'utf-8')

doc.search('some_css_selector').each do |element|
	title = element.search('other_css_selector').text.strip
end
```

## Active Record

### `rake` database methods
* `rake db:create` # Creates your database
* `rake db:drop` # Destroys your whole database
* `rake db:migrate` # Runs any migrations that haven't already been run
* `rake db:version` # Retrieves the current schema version number
* `rake db:seed` # Populates your database with sample data
* `rake db:timestamp` # Gives you a timestamp for your migration file name

### Methods used on Models
* `Model.first` retrieves the first record of Model in the database (depends on the Primary key!)
* `Model.first(10)` ~ `SELECT * FROM models LIMIT 10;`
* `Model.last` retrieves the last record of Model in the database
* `Model.count` retrieves the number of existing instances of `Model`
* `Model.where(title: "example")` returns an Array of Models which column `title` is `example`
* `Model.where(title: ["example", "condition"])` is also valid for multiple conditions on the same column
* `Model.where("title LIKE "%example%")` is the general `WHERE` syntax
* `Model.order(column: :asc)` ~ `SELECT * FROM models ORDER BY column ASC;`

### Models validations
* `validates :order, presence: true` or `absence:` to check the presence or absence of an item
* `validates :email, uniqueness: true` to make sure the item is unique
* `length:` with a `minimum:`, a `maxium:`, a range (`in:`) or an exact value (`is:`)
* `validates :email, confirmation: true` with `validates :email_confirmation, presence: true` for two identical text fields
* `validates :legacy_code, format: { with: /\A[a-zA-Z]+\z/, message: "only allows letters" }` to match regex
* `validates :size, inclusion: { in: %w(small medium large) }` or `exclusion:` to limit or exclude possibilities
* `validates :points, numericality: true` to check a numeric value, with parameters such as `only_integer:`, `equal_to:`, `less_than:`, `ood:`, `even:`...
* `validates :terms_of_service, acceptance: true` for checkboxes
* `validates_associated :books` to make sure associated models also need to be validated

General parameters exist, such as `on:` (to apply on create, update...) and `message:` (to specify error message)
Validations can be conditional, using `if:` or more complex Proc and Lambdas.

