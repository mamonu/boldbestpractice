# 6 QA & testing


Testing is a way of quality assuring our work when creating software that is important. 
Quality means a lot of things and for the scope of this document it will mainly mean reliability.

There is a need to develop a set of tests to provide a proof that our functions work as intended.

Test your functions with specific inputs and expect specific outputs. Start with your testing here. 😊 Unit tests are low level,focusing on testing individual methods and functions used by your scripts.

There are very good testing frameworks that make the creation of tests convenient and not a drag. 
Pytest is recommended for Python (and testthat for R). 

!!! note
  Testing framework libraries:
    - [Pytest](https://docs.pytest.org/) in Python
    - [testthat](https://testthat.r-lib.org/) in R


There are also many Pytest plugins that add new functionality such as coverage calculation, parallelizing tests,
including time information in tests (ie fail a test if it takes more than 1 min to finish!) etc


Tests should be:
  - Fast & Independent
  
  - Repeatable (deterministic)
  
  - Self-validating (no manual steps)

  - Thorough (How much do you trust they cover everything?)
 

