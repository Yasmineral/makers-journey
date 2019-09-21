# Setup

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

# Helpful example

Always try and follow the "Given, When, Then" process:

```
require 'calculator'

describe Calculator do

  # hashtag below to denote instance method
  describe '#add' do
  
    # what do you want the behaviour of your objects to do
      it '1, 2 returns 3' do
      
    # 1. setup (Given)	
      calculator = Calculator.new
      
    #2 execute (When)
      result = calculator.add(1,2)
      
    #3. assert (Then)
      expect(result).to eq 3
      
    #4. teardown to release memory (automatically done, don't worry about this)
    end
  end
end
```

---

# Helpful Features

* You can pass rspec a file path and line number to run specific tests in isolation. It will finds the enclosing tests from the number you give it. This is very helpful when debugging. ```rspec path/to/example_spec.rb:37```

*  RSpec's **subject** is a special variable that refers to the object being tested. When used, we are able to give it a name
and pass a block of code to give us more control over how it is used, e.g
```describe Calculator do
subject(:calculator) {described_class.new}
#described_class wll return the argument passed to it, in this case - calculator
```
It cache's to the setup when it was first declared, so if you want it to behave differently in another test you must write a new declaration for that specific test.

---

# Doubles, Mocks & Stubs

How can you be absolutely sure that your tests are not passing by mistake? Or failing by accident? Enter doubles, mocks & stubs  - flavours of essentially the same idea that don't just improve your tests, but can also improve your design. Good tests have only one variable. What does that mean?

In OOD, we have lots of objects interacting with one another. One object sends a message to another object and maybe that object responds with an answer. Or maybe it changes some internal state. Or maybe it interacts with a third object, or calls some expensive external service, or generates a random result, or...
Sometimes these interactions are predictable. Sometimes they are not. But either way, if I am testing ```ObjectA```, then I don't want my test to be arbitrarily dependent on the behaviour of ```ObjectB```. Particularly if ```ObjectB``` is expensive or complex to instantiate.

* **Doubles**-
Instead of testing ```ObjectA``` against an instance of ```ObjectB```, I use a stand in for ```ObjectB``` instead. ```ObjectA``` doesn't know the difference, it simply treats the double as if were an instance of ```ObjectB```, but it's not - it's a dummy that I've set up with static (and therefore not variable) values.

    * ```double_bike = double("bike")```


* **Stubs**-
I want to test some behaviour of ```ObjectA```, but during the execution of that behaviour, ```ObjectA``` calls a method on ```ObjectB```. I don't need to test that the method on ObjectB gets called, but I do want to make sure that when it does, the method on ```ObjectB``` always returns a specific value.

     * ```double_bike = double("bike")```
     ```allow(bike).to recieve(:broken?).and_return(nil) ```
     * SHORTHAND = ```bike = double(:bike, broken?: nil)```
     
     * e.g raising errors:
     ```describe 'dock' do
     it 'raises an error when full' do
    subject.capacity.times { subject.dock double :bike }
    expect { subject.dock double(:bike) }.to raise_error 'Docking station full'
     end
    end```


* **Mocks**-
I want to test some behaviour of ```ObjectA``` and, critically, during the execution of that behaviour, ```ObjectA``` must call a method on ```ObjectB``` with specific arguments. In my test, I don't particularly care what happens afterwards, but I want to test that in the code that is about to be executed the specific method is called with the correct arguments.
