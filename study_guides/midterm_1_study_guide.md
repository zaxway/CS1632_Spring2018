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
    + 
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
* Testability - requirements must be:
  * Complete, consistent, unambiguous, quantitative, feasible
* Functional vs Non-Functional Requirements  (Quality Attributes)
  * Be able to define and write your own
* Traceability Matrices
  * Be able to define and write your own

## TEST PLANS
* Given a list of requirements, be able to write a test plan
* Terminology: test cases, test plans, test suites, test runs
* Verification vs validation

## DEFECT REPORTING
* Be prepared to report a defect based on a test case
* Remember the defect template:
  * SUMMARY, DESCRIPTION, REPRODUCTION STEPS, EXPECTED BEHAVIOR, OBSERVED BEHAVIOR
  * Optionally: SEVERITY/IMPACT, NOTES
  * Levels of severity: BLOCKER, CRITICAL, MAJOR, NORMAL, MINOR, TRIVIAL
* Coding mistakes vs defects

## Smoke, Exploratory, and Path-based testing
* Define all of these concepts
* I will not ask you to calculate cyclomatic complexity for a given method but I expect you to understand the concept and explain why a method with a higher or lower complexity might be easier/harder to test and why

## AUTOMATED TESTING
* Pros and cons of automated testing
* Unit tests vs system/acceptance/integration tests

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
