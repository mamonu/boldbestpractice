# 5 Reproducible and reusable work

##Functions

Something that also can help is the need to refactor code that is repeating in analysis scripts to a
higher level of abstraction by using reusable functions so that lower-level implementations are wrapped into 
functions and only called by analysis scripts when necessary. 

In this way code becomes easier to reason and to follow through in analysis scripts.



=== "Python"

``` py
def FtoC (temp_in_f):
  celsius = (temp_in_f - 32) * 5/9
  return celcius
```

=== "R"

``` r
FtoC <- (temp_in_fahr - 32) * (5 / 9))
```
## Dependency managment

There is a need to manage project dependencies. This can be done with dependency management tools (Renv for R /Conda for Python).

One solution is using conda for this as it also isntalls libraries in binary format for particular machines (Windows/OSX/Linux).
This is quite useful as a lot of times many packages use what is known as bootstrapping where they are compiled from source code 
to binary on the analyst’s computer. 

Something that is problematic is that most analyst computers are locked down as far as access and writing permissions 
are concerned or they might not include the right C++ compiler. Using conda to install the packages 
needed in already compiled binary format saves a lot of headaches as far as reproducibility is concerned.


## Data and code lineage

Another matter that can help with reproducibility and pays dividends to be aware of is code and data provenance and lineage. 

Different code can understandably give different results. One way to help navigate this is by having 
the output of your analysis to also include the git hash of the code that produced it.

<INSERT WAY TO DO THIS HERE>
  
There is also a need to do the same for data: Analysis that starts from a different point might have a different result. 
The solution is to include a hash of the data or any other way to help identifying the starting point of an analysis. 
MD5 or SH256 can help here
  
example in command prompt:  
  

=== "Windows"
```bash 
  certutil -hashfile <file> MD5
```
  
=== "OSX/Linux"
```bash 
  md5  <file> 
```



