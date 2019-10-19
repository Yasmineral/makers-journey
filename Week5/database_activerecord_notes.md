# Database - SQL

Front end is made up of HTML, CSS & Javascript

Back end / server side is where our Ruby code / Sinatra lives, as well as our .erb template/view files. Servers will query the database with some sort of CRUD.

Persisted data is stored in a database. Essential for storing data that can be accessed even when a session has ended or when your servers go down. 
—
SQL - structured query language for relational databases.
Popular ones include PostgresSQL, SQLite, Oracle which are are open source. Non-relational databases include MongoDB and Cassandra.

Data is organised just like an excel spreadsheet. The columns are your categories and the rows are the actual data you’re putting in.
The id column is an identifier and auto increments with every new entry. It is a way for us to keep track the rows of data. You can use id to point to another table.
What makes it relational is that tables can be ‘joined’ together in many ways to represent complicated sets of data. In SQL we have the power to say ‘this table is related to this other table’ e.g, a User has many Posts.

Databases only understand SQL. It is a special language which allows us to ‘query’ for data that’s stored in the database.  Typing this language can be tedious so often there are frameworks that are made to make our lives easier when dealing with databases, e.g active record. 

# Active record

Active record is a Sinatra db framework & an ORM (object relational mapper). It essentially abstracts the SQL database into some type of interface, sometimes called an API, which can be used in the language of your choice to communicate with that database. Active record abstracts tables into Objects which you can use methods on. It makes performing CRUD a breeze.

Active record gives you loads of features like ‘validates’ which ensures that the user enters valid data otherwise its not stored, and ‘uniqueness’ for things like usernames to enforce unique data. 


**Using Active record**

Models folder - is where our representations of the database tables live. A representation of a singular row of that table.
You can set up your associations here, e.g  ```has_many : kittens``` OR ```belongs_to :owner```. Active record provides this framework and auto’magically’ figures out plurals e.g if you put has_many :mice it would understand that you were talking about a single object mouse.

Class Kitten < ActiveRecord::Base
Inheritance. Kitten is inheriting special powers from active record e.g methods like ```.all``` &  ```.create```.
 
Schema -  a schema describes:
* the blueprint of what tables exist in a database
* What columns the tables will have
* What the relationship between tables are

Stylistically, you don’t want a long list of columns within your table. You may need to split into multiple tables.

When creating models/ interacting with any of your tables, follow this pattern:
* When creating models, class names start with capital letter and are Singular
* If you’re doing any type of association, just think about it in plain English. e.g if the Owner is the one who has many Kittens, then when you set up your association make sure Kittens is plural. Refer to the matching database table that is lowercase and plural. Active record may complain otherwise. 
* There should be a dot (.) after the name of your tale
* What comes after the dot is a function from Active Record that you want to call (e.g which could be the name of a column)

—
Consider downloading ‘tux’ which is an irb for communicating & updating the database using active record, in sinatra.
