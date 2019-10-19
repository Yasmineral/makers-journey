1. Install Gems:

```bash
cd ~/Desktop
mkdir project-name
cd project-name
touch Gemfile
```

```ruby

gem 'pg'
gem 'sinatra-activerecord'
gem 'activerecord'
gem 'rake'
```

2. Connect to database: manually create file **config/database.yml**
```ruby
default: &default
adapter: postgresql
encoding: unicode
pool:

development:
<<: *default
database: db-name-dev

production:
<<: *default
database: db-name

# OPTIONAL
test:
<<: *default
database: db-name-test
```
           
3. Set up database in your terminal
```ruby
rake db:setup
```

4. Create an app.rb file

```ruby
# app.rb
require 'sinatra'
require 'sinatra/activerecord'

set :database_file, 'config/database.yml'
```

5. Create migration file manually: **Rakefile**
```ruby
require 'sinatra/activerecord'
require 'sinatra/activerecord/rake'
require './app'
```

6. Create migration: from command line
```ruby
rake db:create_migration NAME=your_name
```

7. Edit **db/migrate/new_migration_file** (auto loaded) to create your columns
```ruby
def change
  create_table :articles do |t|
  t.string :title
  t.boolean :published, :default => false
  t.datetime :published_on, :required => false
end
```

8. Run the migration from the command line:
```ruby
rake db:migrate
```

9. Create a user model: **models/example.rb**
```ruby
class Example < ActiveRecord:: Base
end
```

10. Load the User model into your app

```ruby
# at the bottom of app.rb
require './models'
```

11. CRUD in your app.rb file using params[:data]


---

Extra stuff:

13. Create a seeds file

```ruby
touch db/seeds.rb
```

14. Write some seeds

```ruby
# db/seeds.rb
users = [
  {fname: 'Jon', lname: 'Doe', email: 'e@example.com'},
  {fname: 'Jane', lname: 'Doe', email: 'e@example.com'}
]

users.each do |u|
  User.create(u)
end
```

15. Run the seeds

```ruby
rake db:seed
```

Create an index.erb file in a views directory (views/index.erb)

```erb
<!DOCTYPE html>
<html>
<head>
    <title>Users</title>
</head>
<body>
    <ul>
        <% @users.each do |user| %>
            <li><%= user.email %></li>
        <% end %>
    </ul>
</body>
</html>
```

16. Create a route for the home page

```ruby
# app.rb
get '/' do
  @users = User.all
  erb :index
end
```

#### Adding more tables (models)

1. Create migration with rake
1. Populate the migration with code for adding columns
1. Run the migration with rake db:migrate
1. Create the model (add class to models file)
1. Add some rows to the table with IRB
1. Create a route and a view for displaying records
       
       
       
      