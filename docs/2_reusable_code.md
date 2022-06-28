
# 2 Reusable code

## Motivation 

Breaking your code down into smaller, more manageable chunks is a sensible way to improve readability and extensibility. Regardless of the language, there are techniques to containerise your code into self-contained parts such as modules or functions. 
Adding repeating, unnecessary code to a codebase *increases the amount of work required to extend and maintain the software in the future*.  Duplicate code adds to [technical debt](https://martinfowler.com/bliki/TechnicalDebt.html).  Whether the duplication stems from "Copy Paste" programming or poor understanding of how to apply abstraction, it decreases the quality of the code. It is hence important to use the DRY `Don't Repeat Yourself` principle in order to create work that is more managable.

!!! info
    DRY (Don't Repeat Yourself) principle: The same piece of code should not be repeated over and over again.

## Functions

In the early stages of analysis we often copy and paste code to ‘make it work’. As this work matures, it is worth taking repetitive code and turning it into functions. Functions allow us to make a piece of logic reusable in a consistent and readable way,
A function is simply a way to “chunk” some code that you can use over and over again, rather than writing it out multiple times. 
Functions enable programmers to break down or decompose a problem into smaller parts, each of which performs a particular task.
In this way code becomes easier to reason and to follow through in analysis scripts. It also provides a way of changing code once if the function inner-workings need to change instead of many repeated times.


### Function Arguments
Information can be passed into functions as arguments.
Arguments are specified after the function name, inside the parentheses. You can add as many arguments as you want, just separate them with a comma.

=== "Python"

``` py
def FtoC (temp_in_fahr):
  celsius = (temp_in_fahr - 32) * (5/9)
  return celcius
```

=== "R"

``` r
FtoC <- function(temp_in_fahr) {(temp_in_fahr - 32) * (5 / 9)}
```

You can find some really helpful pointers on how to create functions in R in the following DASD R Training :

[writing functions in r](https://github.com/moj-analytical-services/writing_functions_in_r)

Likewise a comprehensive tutorial on how to create functions in Python can ve found here:

[defining your own python function](https://realpython.com/defining-your-own-python-function/)


### Referential transparency

When writing functions, it’s  important to consider how they interact with other parts of your code. As a general rule of thumb, your code should run in the same way if a call to your function was replaced by the value that it would have returned. This is referred to as ‘referential transparency’.

In practice, this means that your functions should not depend-on or affect variables that have not been explicitly fed into them as arguments. For instance, a function should not add columns to a data table that has not been passed as an input to the function. Nor should the action of a function be affected by anything other than arguments that are passed to it. For example, running your function twice with the same inputs should always produce the same results.


## Modular design of code and seperation of concerns

By understanding the mechanism of running code that is located in different files the analyst gains the ability
to create modular code that has all related functionality at the same place while achieving `seperation of concerns`
The general idea is that one should avoid co-locating different concerns within the design or code.
`Separation of concerns` tends to be a natural consequence of following the `Don't Repeat Yourself` (DRY) principle

In Python it is well worth understanding the `import` mechanism in order to be able to use not only external packages
but code that is bundled together because it makes sense for it to be co-located. It is worth looking at [this](https://www.pythonlikeyoumeanit.com/Module5_OddsAndEnds/Modules_and_Packages.html) tutorial to understand a bit more about how imports in Python can be used. 

Similarly in R its worth using both the `library` mechanism in order to load external packages and be able to use package functions into the analysis code together with the `source` mechanism in which internal code can be also become available for use. 
The [source](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/source) documentation will be useful.
