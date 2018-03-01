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
    + POSTCONITIONS = assertions
    + assert_equal 1, driver.getBooks(), To declare driver simply say driver = driver::new(1);
    + assert_nil driver.addBooksClassesToys // nil is mainly used for edge cases.
    + assert_includes ["item1", "item2", ...], driver.getDirection("item1"); // used to check if one specific item is listed in the collection of items.
    + assert_true driver.getClasses() // assumes getClasses() is a boolean method, asserts if true.
    + assert_raises 
  * Understand how to write a Minitest unit test (basic syntax)
    + class Driver < Minitest::Test
  * Understand how to make a double
    + Fake objects (I think insert a class inside a testing method)
  * Understand how to make a mock
    + x = 
  * Understand how to make a stub
    + Fake methods, nest a method inside a testing method. 
* Understand difference between mock, double, stub
* Given some Ruby code, be able to perform an equivalence class partitioning and write tests for it

## BREAKING SOFTWARE
* Be prepared to think of happy path vs edge case testing
  + Happy Path Testing = standard path that you take to get the right solution.
  + Edge Case Testing = testing for boundaries inside the input. {1,2,3,4,5,6} 1 and 6 would be our edge cases to test as they are our boundaries. Has to be an unexpected use. 
* What are various ways that software can break?
  + I/O errors = Entering too large of an integer. 
  + Unexpected input
  + Malicious users
  + Null Pointer Errors: Occurs when a variable set to null is dereferrenced to a method that does not accept a null variable.
  + Display Errors: The data is correct, but not displayed correctly. 
  + Bad Data Error: System cannot handle improperly formatted data. 

## TDD
* Basic concepts of test-first development
  + A test driven method that comprises in writing tests before code, writing only code that is tested, writing only tests that test the code, a very short turnaround cycle, refactoring early and often.
  + Test-First: Basic idea is to think about expected behavior first before the code. You don't want to write the code first, and then have to test, write the tests first, then write the code, then run the test suites. 
* The red-green-refactor loop
  + Red: Write a test for new functionality. This test should fail.
  + Green: Write just enough code to make the test pass.
  + Refactor: Review Code and make it better.
* Benefits and drawbacks of TDD
  * When to use it?
    + When we want to make a program that will be repeatedly tested. a very important program.
    + One of the benefits is that it will be done in small steps and that all tests will be relevant.
  * When not to use it?
    + When we want to make a program that is not very important. 
    + One of the drawbacks is that it will take up extra front-up time, so we dont want to use this for simple programs.

## WRITING TESTABLE CODE
* What do we mean by "testable code"?
  + Code that is easy to write and perform tests, both automated and manual, and track down errors when tests fail.
* Basic strategies for testable code
  + Segment Code - make it modular
  + Give yourself something to test
  + Make it repeatable
  + DRY(Don't Repeat Yourself)
  + Write code with seams
* Code segmentation
* "Give yourself something to test"
  + have a reuturn value per method, will give you something very good to test. 
* Pure vs impure methods - be prepared to define and/or determine if a method is pure
  + Pure = output only depends on the input, do nothing else but reutnr a value.
* The DRY Principle
  + Don't copy and paste your code from one function to another. 
  + Don't have multiple methods with the same of similar functionlity. 
* Understand seams
  + Seams are places where behavior can be modified without modifying code.

## Pairwise and Combinatorial testing
* Understand concepts, be able to define
* I will not make you create your own pairwise tests BUT you may be asked to determine if something is a valid pairwise or combinatorial test (i.e., checks all possible t-way interactions)

## PERFORMANCE TESTING
* Understand concepts on how to test performance
* Be able to write test plans for different performance indicators and systems
* Terminology: Service-Oriented vs Efficiency-Oriented Indicators
  + Service Oriented = measures how well a system is providing to its users. They are measured from a specific user's point of view.
  + Efficiency-Oriented = measures how well the system makes use of the computational resources available to them. This is looking a the performance from a more development perspective. (used to find the actual source of the problem) 
* Availability, Response Time, Throughput, Utilization
 + availablity = What percentage of the time can the user use this system?
 + Response Time = How long does the system take to respond to user input?
 + Throughput = How many events can occur and be processed within a given amount of time?
 + Utilization = What percentage or absolute amount of computing resources are used to perform a task? 
* Performance targets, performance thresholds, KPIs - understand and be able to generate!
  + Performance targets = quantitative values that the performance indicators should reach. 
  + KPI (Key Performance Indicator) = a subset of Performance targets that includes the most important targets. 
  + Peformance thresholds = the absolute minimum performance level a system can reach and be considered production-ready. 
* Measuring response time - methodologies
  + includes: time for calculation to finish, time for image to appear, time for file to download, time for server response, etc.
  + All this stuff is believed to be more like a science in that it requires multiple test cases, not just 1. 
* Understand different concepts of time: user, system, total, real
  + user time = amount of time user code takes to execute.
  + system time = amount of time kernel code takes to execute.
  + total time = user time + kernel time
  + real time = actual amount of time taken (wall clock time) {This is what users mainly care about}
* Measuring availability, concurrency, scalability, throughput
  + Measuring availablity
   + Also known as uptime
   + Measured in a form of 9s. i.e. 1 nine = 90% available (36.5 days of donwntime per year), 2 nines = 99% available (3.65 days downtime per year), 3 nines = 99.9% available (8.76 hours of downtime per year), 4 nines, 5 ....
* Understand n 9's (e.g., 5 9s vs 6 9s)
* Load testing - baseline, soak/stability, stress tests
  + Load testing = how many concurrent users and/or work can the system handle?
  + baseline test = a bare minimum amount to use to provide a baseline. 
  + soak/stability test = leave it running for an extended period of time, usually at low levels of usage. 
  + stress test = high levels of activity. 
