
# 2 Reusable code

## Functions


A function is simply a “chunk” of code that you can use over and over again, rather than writing it out multiple times. 
Functions enable programmers to break down or decompose a problem into smaller chunks, each of which performs a particular task.
In this way code becomes easier to reason and to follow through in analysis scripts.


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





