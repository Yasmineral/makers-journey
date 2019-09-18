1. Using the domain model, write the simplest, first feature test for the first user story, using a REPL, to understand how you might interact with the program and the classes, methods, etc you know about so far. Watch the fail (RED step).

2. Write a minimum first unit test, with the aim being to replicate the error that the feature test is producing (RED step).
(These early tests can be scaffold tests to start building out the file and class structure).

3. Write the minimum code to pass the tests - follow the error messages when running the test suite, and fix only what the error is suggesting, i.e.

    * If error reads `NameError : uninstantiated Class` or similar, create the class
    * If error reads `NameError : undefined Method` or similar, create the method
    * If error reads `ArgumentError : expected 0 received 1` or similar, add the necesary number of arguments

4. Follow the next error and keep repeating until the test passes (GREEN step).

5. Refactor code and tests as necessary (REFACTOR step)

6. Regularly run irb or features tests to check expected behaviour.

7. Repeat the process for next requirement.

