1. Install Gems:
       
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

4. Create migration file manually: **Rakefile**
```ruby
require 'sinatra/activerecord'
require 'sinatra/activerecord/rake'
require './app'
```

5. Create migration: from command line
```ruby
rake db:create_migration NAME=your_name
```

6. Edit **db/migrate/new_migration_file** (auto loaded)
```ruby
def change
  create_table :articles do |t|
  t.string :title
  t.boolean :published, :default => false
  t.datetime :published_on, :required => false
end
```

7. Migrate from command line:
```ruby
rake db:migrate
```

8. Create model: **models/example.rb**
```ruby
class Example < ActiveRecord:: Base
end
```

9. CRUD in your app.rb file using params[:data]

10. If you need to delete your tables:
```ruby
rake db:drop
```
       
       
       
      
