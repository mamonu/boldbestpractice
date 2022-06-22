# 7 QA & testing


Testing is a way of quality assuring our work when creating software that is important. 
Quality means a lot of things and for the scope of this document it will mainly mean reliability.

There is a need to develop a set of tests to provide a proof that our functions work as intended.


## Write Tests - Any Tests!
Starting the process of writing tests can be overwhelming, especially if you have a large code base. Further to that, as mentioned, there are many kinds of tests, and implementing all of them can seem like an impossible mountain to climb. That is why the single most important piece of guidance in this chapter is as follows: write some tests. Testing one tiny thing in a code that’s thousands of lines long is infinitely better than testing nothing in a code that’s thousands of lines long. You may not be able to do everything, but doing something is valuable.


Unit tests should be low level,focusing on testing individual methods and functions used by your scripts.
You should try to test your functions with specific inputs and expect specific outputs.  

Make improvements where you can, and do your best to include tests with new code you write even if it’s not feasible to write tests for all the code that’s already written.

## Run the tests
The second most important piece of advice: run the tests. Having a beautiful, perfect test suite is no use if you rarely run it. Leaving long gaps between test runs makes it more difficult to track down what has gone wrong when a test fails because, a lot of the code will have changed. Also, if it has been weeks or months since tests have been run and they fail, it is difficult or impossible to know which results that have been obtained in the mean time are still valid, and which have to be thrown away as they could have been impacted by the bug.

!!! info inline end
      Testing frameworks: [Pytest](https://docs.pytest.org/) is recommended for Python while [testthat](https://testthat.r-lib.org/) is recommmened for R
      
It is best to automate your testing as far as possible. If each test needs to be run individually then that boring painstaking process is likely to get neglected. This can be done by making use of a testing framework 


##  What to test

!!! info 
      Whenever you are tempted to type something into a print statement, write it as a test instead.

- [x] There is a fine balance to writing tests. Each test that you write makes your code less likely to change inadvertently; but it also can make it harder to change your code on purpose. It’s hard to give good general advice about writing tests, but you might find these points helpful:

- [x] Focus on testing the external interface to your functions - if you test the internal interface, then it’s harder to change the implementation in the future because as well as modifying the code, you’ll also need to update all the tests.

- [x] Strive to test each behaviour in one and only one test. Then if that behaviour later changes you only need to update a single test.

- [x] Avoid testing simple code that you’re confident will work. Instead focus your time on code that you’re not sure about, is fragile, or has complicated interdependencies. That said, I often find I make the most mistakes when I falsely assume that the problem is simple and doesn’t need any tests.

- [x] Always write a test when you discover a bug. You may find it helpful to adopt the test-first philosophy. There you always start by writing the tests, and then write the code that makes them pass. This reflects an important problem solving strategy: start by establishing your success criteria, how you know if you’ve solved the problem.





## Consider how long it takes your tests to run
Some tests, like Unit Testing only test a small piece of code and so typically are very fast. However other kinds of tests, such as System Testing which test the entire code from end to end, may take a long time to run depending on the code. As such it can be obstructive to run the entire test suite after each little bit of work. In that case it is better to run lighter weight tests such as unit tests frequently, and longer tests only once per day overnight. It is also good to scale the number of each kind of tests you have in relation to how long they take to run. You should have a lot of unit tests (or other types of tests that are fast) but much fewer tests which take a long time to run.

## Document the tests and how to run them
It is important to provide documentation that describes how to run the tests, both for yourself in case you come back to a project in the future, and for anyone else that may wish to build upon or reproduce your work. This documentation should also cover subjects such as

- Any resources, such as test dataset files that are required

- Any configuration/settings adjustments needed to run the tests

- What software (such as testing frameworks) need to be installed

- Ideally, you would provide scripts to set up and configure any resources that are needed.


!!! note
So to summarise tests should be:
     
- [x] Fast & Independent
  
- [x] Repeatable (deterministic)
  
 - [x] Self-validating (no manual steps)

 - [x] Thorough (How much do you trust they cover everything?)

## Language specific testing tips



=== "Python"
- [x] There are many pytest plugins that add new functionality such as coverage calculation, parallelizing tests,
including time information in tests (ie fail a test if it takes more than 1 min to finish!) etc

=== "R"
- [x] [testthat](https://testthat.r-lib.org/) is the recommended testing solution. You can find an example of how to use it in this [article](https://www.johndcook.com/blog/2013/06/12/example-of-unit-testing-r-code-with-testthat/)
- [x] [assertr](https://docs.ropensci.org/assertr/) library is very useful for data validation. It provides lots of ready made functions for checking data.
- [x] [assertthat](https://github.com/hadley/assertthat) package is a more advanced replacement of the base (ie included always in R) `stopifnot()` function










