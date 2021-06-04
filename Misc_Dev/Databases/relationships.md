## Many to Many
Now, we’re going to add playlists to our app.

Let’s think about the relationship between songs and playlists.

``
A playlist can have many songs. A song can be in many playlists.
``
#### Songs Table
```html
|  id |  title | length | play_count | artist_id |
|-----|--------|--------|------------|-----------|
|  1  | Place  |  345   |  23        |  1        |
|  2  | Bread  |  432   |  12        |  1        |
|  3  | Cherise|  367   |  45        |  2        |
```
#### PlaylistsSongs Table
```html
|  id | playlist_id  | song_id  |
|-----|--------------|----------|
|  1  |      1       |     1    |
|  2  |      1       |     2    |
|  3  |      2       |     3    |
```

#### Playlists Table
```html
| id |      name     |
|----|---------------|
|  1 |  Classic Rock |
|  2 |  Jerry Jams   |
```
**Note:** Join tables are just ordinary tables with a unique purpose. Each row of our join table relates a row of one table to a row of another table.

### Many-to-Many Relationships in Rails
#### Adding Playlists
```ruby
# spec/models/playlist_spec.rb

require "rails_helper"

RSpec.describe Playlist, type: :model do
  describe "relationships" do
    it { should have_many :playlist_songs}
  end
end
```
create our Playlist model:
```ruby
# app/models/playlist.rb

class Playlist < ApplicationRecord
end
```
When we run our tests, we get:
```shell
ActiveRecord::StatementInvalid:
       PG::UndefinedTable: ERROR:  relation "playlists" does not exist
```
Let’s write a migration to create Playlists.

```shell
rails g migration CreatePlaylists name:string
```
Open up that migration and add timestamps to it. Run it with `bundle exec rake db:migrate`.
Running rspec again will give us this failure:
```shell
Failure/Error: it { should have_many :playlist_songs}
       Expected Playlist to have a has_many association called playlist_songs (no association called playlist_songs
```
Let’s go into our model and add that association:
```ruby
class Playlist < ApplicationRecord
  has_many :playlist_songs
end
```
#### Creating the PlaylistSongs Join Table
Let’s start with a test. First we’ll think about what a record in the join table should do. Looking back at our diagram of this table, it should relate a single song with a single playlist:
```ruby
# spec/models/playlist_song_spec.rb
require 'rails_helper'

RSpec.describe PlaylistSong, type: :model do
  describe "relationships" do
    it {should belong_to :playlist}
    it {should belong_to :song}
  end
end
```
Go create the model:
```ruby
# app/models/playlist_song.rb
class PlaylistSong < ApplicationRecord
end
```
Now we’ll generate the migration to create our join table:
```shell
> rails g migration CreatePlaylistSongs song:references playlist:references
> rake db:migrate
```
Run the tests again, and both fail:

```shell
Expected PlaylistSong to have a belongs_to association called playlist (no association called playlist)

Expected PlaylistSong to have a belongs_to association called song (no association called song)
```
Let’s go create those associations:
````ruby
class PlaylistSong < ApplicationRecord
  belongs_to :playlist
  belongs_to :song
end
````
#### A Playlist has many Songs

Run the `playlist_spec` again and it passes! Now that our join table is set up, the connection between the `playlist` and `playlist_songs` is working. Now we can set up the has_many relationship between `songs` and `playlists`. Let’s add this test to our `playlist_spec.rb`:
```ruby
it {should have_many(:songs).through(:playlist_songs)}
```
We are using the ShouldaMatchers `through` method to test that we can access a Playlist’s songs through the join table.
Running this test gives us:
```shell
Failure/Error: it {should have_many(:songs).through(:playlist_songs)}
      Expected Playlist to have a has_many association called songs (no association called songs)
```

Let’s try to add a has_many to our Playlist model:

```ruby
class Playlist < ApplicationRecord
  has_many :playlist_songs
  has_many :songs
end
```
Running this gives us:
```shell
Failure/Error: it { should have_many(:songs).through(:playlist_songs) }
       Expected Playlist to have a has_many association called songs (Song does not have a playlist_id foreign key.)
```
The error is telling us that our songs table doesn’t have a foreign key for playlists. We could be very literal and add a foreign key to songs, but this won’t work per our previous discussion of many to many relationships. Instead, we want to access the songs **through** the join table:

```ruby
class Playlist < ApplicationRecord
  has_many :playlist_songs
  has_many :songs, through: :playlist_songs
end
```
Run this test and it passes!   
Repeat tha for songs

## One to Many
One to many is shown in the above example with the relationship between `PlaylistsSongs` and` Playlists`

`PlaylistSong` has one `Playlist`
````ruby
class PlaylistSong < ApplicationRecord
  belongs_to :playlist
end
````
`Playlist` has many `PlaylistSongs`
```ruby
class Playlist < ApplicationRecord
  has_many :playlist_songs
end
```
Read More on ActiveRecord Associations [here](https://guides.rubyonrails.org/association_basics.html)