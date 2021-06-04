## MVC in Action

### MVC in Action!

For each of the code snippets below, take a few minutes to identify where we are breaking MVC logic conventions.

A bit of context. Imagine that you are working in an app that tracks comedians and their Netflix Specials. Comedians have an age and they also have specials, in a one to many relationship. Specials have a run time which is their length.

### Models
```ruby
class Comedian < ApplicationRecord
  has_many :specials
  
  def self.average_age
    "#{average(:age).round(2)} Years"
  end

  def average_special_runtime
    specials.average(:runtime)
  end
end
```

### Views

```ruby
<% @comedians.each do |comic| %>
<h4><%= comic.specials.count %> Specials</h4>
<% end %>
```
### Controllers
```ruby
class ComediansController < ApplicationController
  def index
    @comedians = Comedian.all
    @average_age = Comedian.average(:age)
  end
end
```
```ruby
class ComediansController < ApplicationController
  def show
    @comedian = Comedian.find(params[:id])
    @average_special_runtime = @comedian.average_special_runtime.round(2)
  end
end
```