# Week 1 goals
* Test-drive a simple program using objects and methods
  * RSpec / objects and methods / TDD process
* Pair using the driver-navigator style
  * good pairing practices (driver navigator, ping-pong, oneundermanship)
* Describe some basic OO principles
* Follow an effective debugging practice

# Wider week goals
* I can TDD anything
  * You should be able to write a meaningful test, based on the user requirements. You'll then be able to write code using TDD, to make the test pass.
* I can program fluently
  * Learn how to setup and structure a new Ruby project, and turn user requirements into working code.
* I can debug anything
  * You'll be introduced to a technique for uncovering the root-cause of bugs in your code. When your code doesn't work, you'll be able to apply a consistent process to resolve the issue.  
  
# Advice from past cohorts
* Work on problem-solving methodology asap
* Try putting an hour aside when home to learn something more in-depth, ‘hour of power’
* Don’t get wasted at weekends, this is only 3 months - don’t waste it
* Start documenting learnings
* Measure your success using things that you have learnt as opposed to the amount of work that you have completed 
* Get comfortable with not finishing anything and take what learning you can from each challenge
* Understand the difference between what to test and what not to test. TDD is important, and can really help get the ball rolling when tackling your first couple of assignments
* Message coaches for help when blocked
* Aim to do a professional review half way through the course

---
**Tuesday 17th September**

Alice led a debugging workshop with the below exercise, where there are three bugs to fix: https://github.com/Hives/skills-workshops/tree/master/week-1/debugging_1

Learnings:
* **Get visibility** - use `p` or `puts` to output variables 
* **Tighten the loop** - hone in on where the bug is coming from
* Understand where the bug is coming from before trying to fix it
* Your error messages are very useful - pay attention to them / google them
* Your stack trace is the order of calls made by the program

---
**Thursday 19th September**

Ed led the morning workshop with lessons & wisdom on TDD practices. We were asked to follow TDD processes to build a dice game - https://github.com/makersacademy/skills-workshops/blob/master/week-1/TDD_process.md. 

Learnings:
* Set your acceptance criteria to define what your final program when it's ‘done’ looks like. Ideally, write that in code based on the user requirements. Then write your tests to assert this.
* By default, always choose the simplest things to test first. Don’t over complicate things. This is the sign of a good dev. 
* Feature test - replicate how its going to work from the point of view of who’s using the program. At the moment, we’re taking the place of the user so we’re using manual feature tests in irb. In the future, these will be automated with a test test framework.
* Where possible, don’t use ‘respond_to’ in your tests as it is quickly made redundant, e.g if it’s giving back the wrong method / one that isn’t needed. You will end up with brittle tests. It's more important to test return values (the behaviour of the object). We’re not interested in state at this point. 
* Don’t believe all user stories! You may need to tweak to make them more logical.
* Try to not change too much of your code when introducing new things to implement and test for. You want to aim to be ‘scaffolding’ code onto your exisiting program. Otherwise, all your tests may need rewriting.


---
# Boris Bikes

**User Stories to Domain Model**

A **User Story** describes one thing a program is expected to do, from the perspective of somebody using that program.
Much of a developer's life is spent translating User Stories into a functional system. In Object-Oriented Programming, these systems are made up of Objects and Messages. Objects describe the objects within the system, and Messages describe how those objects interact. We call these systems **Domain Models**.

**TDD Process**
1. Write user stories from the requirements
    * These should be user-centric, with a clear statement of value that this feature will give them

2. Extract the nouns and verbs from the first user story
    * Nouns are the objects, verbs are the messages or methods to send to the objects

4. Build a table of the objects and methods. For example...

| Objects       | Methods           
| ------------- |:-------------:|
| controller    |               |
| passenger     |               |
| plane         | flying?       |
| airport       | land_plane    |

5. Map the methods to objects to see which messages can be sent to which objects

6. Draw out how they need to interact (and how the individual objects should encapsulate their concerns)

7. How would the user expect to use the program - run through an example in a REPL

8. Write down a series of the simplest things to build up from (these could eventually become your tests)

9. Each object can be a separate file

10. Further modelling can support a greater understanding of the problem, how the domain is structured, and how the parts of the eventual solution need to interact. This can include:
    * Class models to represent the relationships between objects in your model
    * Sequence diagrams to model each delegation to a different object or system with your application. They highlight information about what each message returns and what objects will call them
    

[See also - General TDD](../week1/TDD.md)
