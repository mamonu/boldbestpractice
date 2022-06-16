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


# Data is immutable

- Don't ever edit your raw data, especially not manually, and especially not in Excel. Don't overwrite your raw data. Don't save multiple versions of the raw data. Treat the data (and its format) as immutable. 
- The code you write should move the raw data through a pipeline to your final analysis. 
- You shouldn't have to run all of the steps every time you want to make a new figure 



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

  
# Keep data out of version control

You really don't want to leak your data on a public repo on Github.  Here's one way to do this:

Learn how to use `.gitignore`. In this way data files should never get committed into the version control repository. 

  
  
# Keep secrets and configuration out of version control

You also don't want to leak your AWS secret key or database username and password on Github.  Here's one way to do this:

- Store your secrets and config variables in a special file
- Create a .env file in the project root folder. Thanks to the `.gitignore`, this file should never get committed into the version control repository. 
