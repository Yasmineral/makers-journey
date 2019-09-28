# Gemfile

A Gemfile is a file we create which is used for describing gem dependencies for Ruby programs. A gem is a collection of Ruby code that we can extract into a “collection” which we can call later.
It is useful to note that your Gemfile is evaluated as Ruby code. When it is evaluated by Bundler the context it is in allows us access to certain methods that we will use to explain our gem requirements.

**Setting up a Gemfile**

Your Gemfile should always be in the root of your project directory, this is where Bundler expects it to be and it is the standard place for any package manager style files to live.

* The first thing we need to do is tell the Gemfile where to look for gems, this is called the source - ```source "https://rubygems.org”```
  * It isn’t recommended to have more than one source per project. For 99% of projects that require a Gemfile your source will be set to https://rubygems.org. The only requirement for a source is that it must be a valid Rubygems repository.

* If the application you are creating requires a specific Ruby version or engine we can set this in the Gemfile - ```ruby "1.9.3"```

* Then you set up them Gem! The most basic syntax is ```gem "my_gem"```
  * The most common thing you will want to do with a gem is set its version. If you don’t set a version you are basically saying any version will do - ```gem "my_gem", ">= 0.0"```. There are seven operators you can use when specifying your gems, research depending on what you require.
  
* Grouping - a gem can belong to one or more groups. When it doesn’t belong to any groups it is put into the ```:default``` group. 
  * There are two ways you group a gem. The first is by assigning a value to the ```:group property; gem "my_gem", group: :development```. This means it will only be required when the development environment is running.
  * The second way you can decide a grouping for a gem is by setting your gems up inside a block, which is visually more pleasing, and you can combine groups - 
  ```group :development, :test do
  gem "my_gem"
  gem "my_other_gem"```
  
* The very last step of the process is to run bundle. This will invoke bundler, the dependency manager, that will look into Gemfile, see if any of the gems need to be installed (they may already be installed), install them and save the information about the gems, their versions and dependencies into an automatically generated ```Gemfile.lock```.

**Bundle**

Bundler: The best way to manage a Ruby application's gems. Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed. Bundler is an exit from dependency hell, and ensures that the gems you need are present in development, staging, and production.

