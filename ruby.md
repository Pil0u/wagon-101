# Ruby 101

This page was written following Le Wagon's internal resources.

## Official Ruby doc (2.6.5)

### Basic classes
* [Array](https://ruby-doc.org/core-2.6.5/Array.html/)
* [Enumerable](https://ruby-doc.org/core-2.6.5/Enumerable.html/)
* [Integer](https://ruby-doc.org/core-2.6.5/Integer.html/)
* [Float](https://ruby-doc.org/core-2.6.5/Float.html/)
* [String](https://ruby-doc.org/core-2.6.5/String.html/)
* [Symbol](https://ruby-doc.org/core-2.6.5/Symbol.html/)

### Utilities
* [Exception](https://ruby-doc.org/core-2.6.5/Exception.html/)
* [File](https://ruby-doc.org/core-2.6.5/File.html/)
* [IO](https://ruby-doc.org/core-2.6.5/IO.html/)
* [Random](https://ruby-doc.org/core-2.6.5/Random.html/)
* [Regexp](https://ruby-doc.org/core-2.6.5/Regexp.html/)
* [Time](https://ruby-doc.org/core-2.6.5/Time.html/)

## Active Record

`rake` database methods:
* `rake db:create` # Creates your database
* `rake db:drop` # Destroys your whole database
* `rake db:migrate` # Runs any migrations that haven't already been run
* `rake db:version` # Retrieves the current schema version number
* `rake db:seed` # Populates your database with sample data
* `rake db:timestamp` # Gives you a timestamp for your migration file name

Methods that can be used on Models:
* `Model.first` retrieves the first record of Model in the database (depends on the Primary key!)
* `Model.first(10)` ~ `SELECT * FROM models LIMIT 10;`
* `Model.last` retrieves the last record of Model in the database
* `Model.count` retrieves the number of existing instances of `Model`
* `Model.where(title: "example")` returns an Array of Models which column `title` is `example`
* `Model.where(title: ["example", "condition"])` is also valid for multiple conditions on the same column
* `Model.where("title LIKE "%example%")` is the general `WHERE` syntax
* `Model.order(column: :asc)` ~ `SELECT * FROM models ORDER BY column ASC;`


