# Advice from past cohorts

* Work on problem-solving methodology asap
* Try putting an hour aside when home to learn something more in-depth. ‘hour of power’
* Don’t get wasted at weekends, this is only 3 months, don’t waste it
* Start documenting learnings and working on a thesis
* Measure your success using things that you have learnt as opposed to the amount of work that you have completed 
* Get comfortable with not finishing anything and take what learning you can from each challenge
* Understanding the difference between what to test and what not to test. TDD is important, and can really help get the ball rolling when tackling your first couple of assignments
* Message coaches for help when blocked
* Aim to do a professional review half way through the course

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

Object	Methods
controller	
passenger	
plane	flying?
airport	land_plane (make into table)

5. Map the methods to objects to see which messages can be sent to which objects

6. Draw out how they need to interact (and how the individual objects should encapsulate their concerns)

7. How would the user expect to use the program - run through an example in a REPL

8. Write down a series of the simplest things to build up from (these could eventually become your tests)

9. Each object can be a separate file

10. Further modelling can support a greater understanding of the problem, how the domain is structured, and how the parts of the eventual solution need to interact. This can include:
  * Class models to represent the relationships between objects in your model
  * Sequence diagrams to model each delegation to a different object or system with your application. They highlight information about what each message returns and what objects will call them
