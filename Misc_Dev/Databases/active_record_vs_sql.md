## SQL and ActiveRecord

### Learning Goals
* Write SQL statements using select, where, order, limit, and distinct. 
* Translate SQL statements into ActiveRecord

### Vocabulary
* SQL
* ActiveRecord
* Tables
* Rows
* Columns
* Keyword Arguments

## Lesson
In this lesson, we will be writing both raw SQL and ActiveRecord.  
In the terminal run, 
```shell
$ bundle exec rails console
```

### Select all records from a table
Assuming you have a songs table in the database,  we can get all of the Song entries in the database with:
```postgresql
SELECT * FROM songs;
```
which is equivalent to  
```ruby
Song.all
```
A couple of things to note here:
* In ActiveRecord, we use the model, Song, to start our queries, even though the table is called songs.
* We don’t have to write the from clause in ActiveRecord. ActiveRecord will assume that you are working with the table associated with the model you’re using. In this case, the Song model is associated with the songs table.
* We also don’t have to write the select clause. ActiveRecord assumes you are selecting everything from the table you’re working with.

## Selecting specific columns
in SQL,
```postgresql
SELECT songs.title FROM songs;
```

in AR

```ruby
Song.select(:title) or Song.select("title")
```

Notice that this is returning an instance of `ActiveRecord::Relation`. We know our sql statements return tables, which ActiveRecord represents as `ActiveRecord::Relation` objects. You can think of it as an Array where each element is a row. We can interact with it like so:

```shell
> songs = Song.select("title")
=> #<ActiveRecord::Relation [#<Song id: nil, title: "Don't Stop Believin'">, #<Song id: nil, title: "Don't Worry Be Happy">, #<Song id: nil, title: "Chicken Fried">, #<Song id: nil, title: "Radioactive">]>
> songs.first
=> #<Song id: nil, title: "Don't Stop Believin'">

> songs[1]
=> #<Song id: nil, title: "Don't Worry Be Happy">
```

Notice how each of the Songs in this relation is missing values for `id`, `length`, and `play_count`. That’s because we only selected the title. This is equivalent to how the sql statement returned a table with one column.
### Pluck

It’s important to understand how to work with `ActiveRecord::Relation` objects, but if you just want all the values out of a column as an Array, ActiveRecord has a shortcut:

```shell
> Song.pluck(:title)
=> ["Don't Stop Believin'", "Don't Worry Be Happy", "Chicken Fried", "Radioactive"]
```

## Selecting specific rows
#### SQL
In the previous examples, we were selecting data from all rows, but what if we only want specific rows? For example, what if we wanted to get Songs with a title of “Radioactive”?
```postgresql
select * from songs where songs.title = 'Radioactive';
```

We can also do comparisons in sql. What if we wanted to get songs with a length greater than 200?

```postgresql
select * from songs where songs.length > 200;
```

#### Active Record
We can use `where` clauses in ActiveRecord as well:
```shell
> Song.where(title: "Radioactive")
=> #<ActiveRecord::Relation [#<Song id: 4, title: "Radioactive", length: 10000, play_count: 623547, created_at: "2019-04-22 22:22:01", updated_at: "2019-04-22 22:22:01">]>
```
```shell
> Song.where("length > 90")
=> #<ActiveRecord::Relation [#<Song id: 1, title: "Don't Stop Believin'", length: 251, play_count: 760847, created_at: "2019-04-22 22:22:00", updated_at: "2019-04-22 22:22:00">, #<Song id: 2, title: "Don't Worry Be Happy", length: 280, play_count: 65862, created_at: "2019-04-22 22:22:00", updated_at: "2019-04-22 22:22:00">, #<Song id: 4, title: "Radioactive", length: 10000, play_count: 623547, created_at: "2019-04-22 22:22:01", updated_at: "2019-04-22 22:22:01">]>
```

## Ordering rows
#### SQL
```postgresql
select * from songs order by title;
```
In descending order:
```postgresql
select * from songs order by title desc;
```

#### ActiveRecord
```shell
Song.order(:title)
```

```shell
Song.order(:title :desc)
```
## Limiting Rows
#### SQL
```postgresql
select * from songs limit 2;
```

#### Active Record
```shell
Song.limit(2)
```

## Distinct Rows
#### SQL
```postgresql
select distinct songs.title from songs;
```

#### Active Record
```shell
> Song.select(:title).distinct
```

### Putting it Together
Let’s say we want to get the titles of the two Songs with the longest length that have at least 60,000 plays. Let’s break this down:

* “get the titles” = `select songs.title from songs`
* “of the two songs” = `limit 2`
* “with the longest length” = `order by length desc`
* “that have at least 60,000 plays” = `where play_count >= 60000`

#### In SQL
```postgresql
select songs.title from songs
where play_count >= 60000
order by length desc
limit 2;
```
As your sql/AR statements get longer, it is helpful to write each clause on its own line.
Once you know the sql you want to execute, then we can translate to ActiveRecord. The below is the ActiveRecord version of the above.
```shell
> Song.select(:title)
    .where("play_count >= 60000")
    .order("length desc")
    .limit(2)
```
Unlike sql, the order of the ActiveRecord methods does not matter. For example, we can reverse the order and achieve the same output

```shell
> Song.limit(2)
    .order("length desc")
    .where("play_count >= 60000")
    .select(:title)
```
This is illustrating a very important fact about ActiveRecord queries. **ActiveRecord will take methods chained together and execute them as a single SQL statement**. This behavior is different than what we normally see in Ruby where chained methods execute left to right, and the next method is called on the return value of the previous method.

### Practice

Write the following in SQL, then ActiveRecord. See the beginning of the lesson plan for help opening psql and rails console connections.

1. Get all songs
1. Get all the song lengths
1. Get the songs with a play count greater than zero.
1. Get the titles of the songs with a play count greater than zero.
1. Get the titles of the songs with a play count greater than zero, sorted alphabetically.
1. Get the titles of the songs with a play count greater than zero, sorted reverse alphabetically.
1. Get the titles of the two songs with a play count greater than zero, sorted reverse alphabetically.
1. Get the length of the song with the most plays.

Read More from ActiveRecord documentation [here](https://guides.rubyonrails.org/active_record_basics.html)

