# 6 QA & testing


Testing is a way of quality assuring our work when creating software that is important. 
Quality means a lot of things and for the scope of this document it will mainly mean reliability.

There is a need to develop a set of tests to provide a proof that our functions work as intended.

!!! info inline end
      Testing framework libraries:
      [Pytest](https://docs.pytest.org/) is recommended for Python
      [testthat](https://testthat.r-lib.org/) is recommmened for R


There are very good testing frameworks that make the creation of tests convenient and not a drag. 



Tests should be:
  - Fast & Independent
  
  - Repeatable (deterministic)
  
  - Self-validating (no manual steps)

  - Thorough (How much do you trust they cover everything?)
 

Test functions with specific inputs and expect specific outputs.  

Unit tests should be low level,focusing on testing individual methods and functions used by your scripts.


## pytest plugins

There are many pytest plugins that add new functionality such as coverage calculation, parallelizing tests,
including time information in tests (ie fail a test if it takes more than 1 min to finish!) etc
