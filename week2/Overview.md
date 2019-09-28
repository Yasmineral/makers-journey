# Week 2

# Goals

* Break one class into two classes that work together, whilst maintaining test coverage
* Unit test classes in isolation using mocking
* Explain some basic OO principles and tie them to high level concerns (e.g. ease of change)
* Review another person's code and give them meaningful feedback
* Use all of week 1's skills

# Advice from past cohorts

* A method and a class should have a single responsibility. Only use 'and' when describing it's responsibility if it is delegating this second responsibility elsewhere. But watch out - it shouldn't delegate everything. Develop skills to know when to ```delegate``` & when to ```encapsulate```.
* Try to return something from your methods (object, etc) that can be logically used and tested.
* Try to refrain from using puts (e.g.) unless building an UI component, otherwise should be pure logic.
* Test behaviour at limits (i.e. test ```can I land 20 planes?``` and ```can I land more than 20 planes?```)
* Fully double any object that isn't the one under test, so we can be sure that the test is testing the behaviour of one and only one object.
* Dependency injection is useful, look into this.

```ruby
class Airport
  def initialize(capacity, weather)
    @capacity = capacity || 20          <- if no arg will default to 20
    @weather = weather || Weather.new   <- injects Weather if no arg provided
  end
end

Airport.new(nil, weather_double)
```

---
**Mon 24th Sep**

Weekend challange code review with Michael. Take aways:

* Air on the side of keeping error messages for truly unexpected and undesired behaviour, e.g - landing or taking off twice is unexpected so raise an error then.
* Consider changing the error clauses to return a boolean value. 
* Don't use errors and rescues to control flow in a program - bad design. 
* It's useful to set up your error messages in the following format: 1. What the error is / what you can’t do 2. what the problem is 3. advice to the user for how to fix it


