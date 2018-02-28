# CS 1632 Midterm 1 Exam Study Guide - Spring 2018

The midterm is on 28 FEB 2018 (M/W classes) or 1 MAR (T/H class).

The midterm will cover everything we have covered up to the exerise the class before.  I recommend you review the slides and the textbook (see syllabus.md for reminders of which chapters were required reading).

Here are the key topics to study in preparation for the test.

## TESTING THEORY AND TERMINOLOGY
* Equivalence class partitioning
  + An equivalence class is a natural grouping of values with similar behavior or belonging to the same category.
  + Ex) For all Positive numbers --> {1,2,3,4,5,6} belongs in the set. 
  + Ex) You do not follow person A on Twitter --> you do not see person A's tweet. 
  + Ex) You do follow person A on Twitter --> you see their tweet.
  
* Boundary and interior values
  + Problems are more prevalent on the boundary than in the middle.
  + Boundary Values include: MAXINT, MININT, undefined values, allocation limitation, and maximum precision of a floating       point value
  
* Base, Edge, and Corner cases
  + Base case = not around the boundary (expected use case)
  + Edge Case = next to the boundary (unexpected use case)
  + Corner Case = A case that occurs only outside of normal operating paramters (combination of multiple edge cases)
  
* Static vs Dynamic testing
  * Know the differences and examples of each
    + Static Testing = The code is reviewed by the person without the code actually being executed (includes source code analysis)
    + Dynamic Testing = The code is actually being executed and we are testing how the code actually functions. Industry uses dynamic testing much more often as it is more efficient than static. 
* Black/White/Grey box testing
  * Know the differences and examples of each
    + Black Box Testing = Testing with no knowledge of the interior system structure. Tests are based on the user's perspective looking at the system as a whole kind of what we did in deliverable #1.
      + Tests include accessing a website, using a browser to look for flaws, running a script against an API endpoint, checking to see that changing fonts in a word processor returns the correct font.
    + White Box Testing = Testing with explicit knowledge of the interior system structure and codebase. Tests directly with the code. Tests are often lower level and deals with testing individual methods kind of like what we did in deliverable #2.
      + Tests include testing a function returns the correct value. testing that instantiating an object creates a valid object.
    + Grey Box Testing = Testing with knowledge of the interior system structure and codebase of the system under test, but NOT directly testing with the code. Tests are similar to black box testing. 
      + Tests include reviewing code, and then noticing that bubble sort is being used, then writing a user facing test involving a large input size.

## REQUIREMENTS ANALYSIS
* What makes a good or bad requirement?
  + Requirements specify what to do, not how to do it. 
  + Leave it to the programmer to figure out the "how" side of things. 
  
* Testability - requirements must be:
  * Complete, consistent, unambiguous, quantitative, feasible
      + Complete
        + Requirements should cover all aspects of the system.
      + Consistent
        + Requirements should not contradict each other.
        + Ex) Requirement 1 states that the bird cage should close its door when the bird goes inside the cage. Requirement 2 then states that the bird cage should open its door when the bird goes inside the cage. --> As such these two requirements are not consistent. 
      + Unambiguous
        + Specify what the "default values" or "specification values" are. 
      + Quantitative
        + Ex) Bad: The system will be responsive to the user.
        +     Good: The system will respond to the user is less than one second for at least 99% of all expected queries.
      + Feasible to Test
        + Just basically means that the requirement shall be possible to test in an appearing possible amount of time, so tests that take 10000 years or more memory than our current system can hold, it is not possbile to test. 
        
* Functional vs Non-Functional Requirements  (Quality Attributes)
  * Be able to define and write your own
    + Function Requirement = The system must DO something. 
    + Quality Attribute = The system must BE something. 
* Traceability Matrices
  * Be able to define and write your own
    + Simply maps requirements to each of our test cases. 

## TEST PLANS
* Given a list of requirements, be able to write a test plan
  + Test-Case Identifier: Name of test case.
  + Description: Describes what the test does.
  + Preconditions: What must happen before this test can run as planned.
  + Execution Steps: How do we execute this test?
  + Postconditions: What kind of result should the test return for it to be a success(We do not care about what it exactly returns once we test it)
  
* Terminology: test cases, test plans, test suites, test runs
  + test suites: collection of test cases used to check a specific requirement.
* Verification vs validation
  + Verifciation: Ensures that the requirements are met.
  + Validation: Ensures that the software built meets the customer's requirements as in whatever product they built is what the customer wants. 

## DEFECT REPORTING
* Be prepared to report a defect based on a test case
  + Summary: Probvides one sentence about the problem
  + Description: Provides a lot more detail about the problem.
  + Reproduction Steps: provides a step by step procedure on how to get to the error.
  + Expected behavior: what is supposed to happen?
  + Observed behavior: what actually happens? 
* Remember the defect template:
  * SUMMARY, DESCRIPTION, REPRODUCTION STEPS, EXPECTED BEHAVIOR, OBSERVED BEHAVIOR
  * Optionally: SEVERITY/IMPACT, NOTES
  * Levels of severity: BLOCKER, CRITICAL, MAJOR, NORMAL, MINOR, TRIVIAL
* Coding mistakes vs defects

## Smoke, Exploratory, and Path-based testing
* Define all of these concepts
  + Exploratory Testing: testing wihtout a test plan, goal is to simply explore the execution of the software.
  + Smoke Testing: Making sure a few tests pass before we actually create an entire test plan for the software we are trying to test. 
  + Path-Based Testing: Testing all possible paths to a piece of software.
    + Example: Take a racing game for example with a red car and a blue car. One path could be: Red Car crosses the finish line --> Red Car wins the race --> Blue car loses the race
      
* I will not ask you to calculate cyclomatic complexity for a given method but I expect you to understand the concept and explain why a method with a higher or lower complexity might be easier/harder to test and why
  + A method with higher complexity will have a lot more paths, making it harder to test because we would need to traverse each path. It would also yield a greater possibility of defects. A program with lower complexity would have a less chance for defects. 

## AUTOMATED TESTING
* Pros and cons of automated testing
  + Pros
    1. Human error is thrown out of the window.
    2. Fast test execution
    3. Easy to set up
  + Cons
    1. Requires extra time up front.
    2. May not catch some user-facing bugs. 
    3. It only tests what it is looking for.
    4. Requires more skilled developers.
* Unit tests vs system/acceptance/integration tests
  +  Unit Testing ensures that the smallest pieces of code works correctly. 

## UNIT TESTING
* Unit tests
  * Pay special attention to assertions
  * Understand how to write a Minitest unit test (basic syntax)
  * Understand how to make a double
  * Understand how to make a mock
  * Understand how to make a stub
* Understand difference between mock, double, stub
* Given some Ruby code, be able to perform an equivalence class partitioning and write tests for it

## BREAKING SOFTWARE
* Be prepared to think of happy path vs edge case testing
* What are various ways that software can break?

## TDD
* Basic concepts of test-first development
* The red-green-refactor loop
* Benefits and drawbacks of TDD
  * When to use it?
  * When not to use it?

## WRITING TESTABLE CODE
* What do we mean by "testable code"?
* Basic strategies for testable code
* Code segmentation
* "Give yourself something to test"
* Pure vs impure methods - be prepared to define and/or determine if a method is pure
* The DRY Principle
* Understand seams

## Pairwise and Combinatorial testing
* Understand concepts, be able to define
* I will not make you create your own pairwise tests BUT you may be asked to determine if something is a valid pairwise or combinatorial test (i.e., checks all possible t-way interactions)

## PERFORMANCE TESTING
* Understand concepts on how to test performance
* Be able to write test plans for different performance indicators and systems
* Terminology: Service-Oriented vs Efficiency-Oriented Indicators
* Availability, Response Time, Throughput, Utilization
* Performance targets, performance thresholds, KPIs - understand and be able to generate!
* Measuring response time - methodologies
* Understand different concepts of time: user, system, total, real
* Measuring availability, concurrency, scalability, throughput
* Understand n 9's (e.g., 5 9s vs 6 9s)
* Load testing - baseline, soak/stability, stress tests
