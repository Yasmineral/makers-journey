**Basics**

RSpec is one of the most used Behaviour Driven Development tools in the ruby community.

Before we start you will need to install RSpec on your machine.

```gem install rspec```
Once you have installed RSpec you can see the different options of RSpec running the help command.

Initilaise Rspec.
```rspec --init```

```rspec --help```
Note that RSpec consists of three main components:
* RSpec Core Docs
* RSpec Expectation Docs
* RSpec Mock Docs

***

When working on a project though you will not have your specs side by side with your production code. A common directory structure in a project looks more like this:

```
      ├── lib
      │   └── greeter.rb
      └── spec
          └── greeter_spec.rb
         
```         
          
This way you are clearly separating your real code from your testing code. There is another tangible benefit to this, in your spec file you now can require the file under test much easier:

```require 'greeter' # No need for that ugly './' ``` anymore. Another added benefit is that you can now run RSpec from the top level directory of your project without needing to specify the spec files you want to be running

```rspec``` RSpec will figure out which files are in the lib directory and which are in the spec directory and will map those with each other (with help of your requires of course) so that you can run your specs.

---

