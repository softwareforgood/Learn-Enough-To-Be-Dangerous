## Dynamic Routing

### Learning Goals

- Understand how data is dynamically passed using Routes
- Create a show page
- Use ActiveRecord to retrieve a single object from the database by its id
### Routing and Route Segments

The Rails Router is a pattern matcher. When our app receives an incoming HTTP request, the Router will match the request’s `verb` and `path` to one of our routes. The first one it matches, it will run the specified `controller#action`. If no route matches, our app will throw an error.

Furthermore, a `path` can be separated into segments, each one separate by a slash /. For example, if we had a route in routes.rb:

```ruby
get ‘/show/me/the/songs’, to: songs#show_em
```
We would say this route has 4 segments: `show, me, the, songs`. When the Router is try to match an incoming HTTP request’s path to one of our routes, each segment needs to match in the correct order. For our example route:

Only a GET request to /show/me/the/songs would match this route
- GET to `show/me/some/songs` would not match
- GET to `show/me/songs` would not match
- GET to `show/me/the/songs/please` would not match
- GET to `show/the/me/songs` would not match
- POST to `show/me/the/songs` would not match

### Dynamic Segments

Your routes can also include dynamic segments. These are segments which can accept any value for that segment.

We define a dynamic segment with a colon :. Let’s revisit our example route and make the second segment dynamic:

```ruby
get ‘/show/:me/the/songs’, to: songs#show_em
```
Now that the second segment `:me` is dynamic, any value in that second segment will match this route:

- A GET request to /show/brian/the/songs would match
- A GET request to /show/129482/the/songs would match
- A GET request to /show/me/the/songs would match
- A GET request to /show/:me/the/songs would match
- A GET request to /show/the/me/songs would not match
Note that the dynamic segment looks like a symbol, and may even be referred to as a symbol, but technically it is not a symbol.

