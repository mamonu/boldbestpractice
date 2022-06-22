# 6 Reproducible work

One of the problems with working with open source software is that it is quite easy to fall into a trap called ‘dependency hell’. Essentially, this occurs when the software we write depends on open source packages, which depend on other open source packages, which can depend on other packages, and on, and on.

All these packages may be written by many different people, and are updated at vastly different timescales. If we fail to take account of this, then we are likely to fail at the first hurdle of reproducibility, and we may find that in a year’s time we are no longer able to reproduce the work that we previously did - or at least not without a lot of trouble. There are several ways we might get on top of this problem and we in this way we are going to try to explain some ways of dealing with this.


## Dependencies

`Dependencies` are all of the software components required by your project in order for it to work as intended and avoid runtime errors.


=== "Python"


After installing the following packages

```bash
pip3 install pipreqs
pip3 install pip-tools
```

Use the following code to build a deterministic `requirements.txt` in the root folder of your project. That will find all
requirements needed for your project to run which will be useful at a later point when dependency managment tools are going to be used. 


```bash
 pipreqs --savepath=requirements.in && pip-compile
```
=== "R"

By typing 

```r
sessionInfo()
```
on your console you can find information about your R script's dependencies. This information is going to be really useful at a later point


## Dependency managment

As seen above when working on a code project, one of the key concerns is `dependency management`.  This usually means dealing with the specific packages/libraries and specific package/library versions needed for a program to run sucessfully

This can be done effectively with dependency management tools:


=== "Python"
A tried and tested solution is using [conda](https://docs.conda.io/en/latest/) for this as it also installs libraries in binary format for particular machines (Windows/OSX/Linux). This is quite useful as a lot of times many packages use what is known as bootstrapping where they are compiled from source code to executable packages that can be then imported on the analyst’s computer. 
Something that is can usually become a problem is that most computers analysts use are locked down as far as access and writing permissions 
are concerned or they might not include the right C++ compiler. Using conda to install the packages needed in already compiled binary format saves a lot of headaches as far as reproducibility is concerned.
=== "R"
Using a dependency managment tool like [Renv](https://rstudio.github.io/renv/articles/renv.html) is recommended for R.


## Data is immutable

- Don't ever edit your raw data, especially not manually, and especially not in Excel. Don't overwrite your raw data. Don't save multiple versions of the raw data. Treat the data (and its format) as immutable. 
- The code you write should move the raw data through a pipeline to your final analysis. 
- You shouldn't have to run all of the steps every time you want to make a new figure 



## Data and code lineage


Another matter that can help with reproducibility and pays dividends to be aware of is code and data provenance and lineage. 

### Code lineage

Different code can understandably give different results. One way to help navigate this is by having 
the output of your analysis to also include the git hash of the code that produced it.

=== "Python"
```py 
import subprocess
def get_git_revision_hash():
    return subprocess.check_output(['git', 'rev-parse', 'HEAD'])
def get_git_revision_short_hash():
    return subprocess.check_output(['git', 'rev-parse', '--short', 'HEAD'])
```
  
=== "R"
```r 
library(git2r)
repo <- repository(".")
print(repository_head(repo))
```

### Data lineage
  
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

  
### Keep data out of version control

You really don't want to leak your data on a public repo on Github. The way to do this is to learn use `.gitignore`. 
In this way data files should never get committed into the version control repository. 
You can see below hypothetical .gitignore examples for Python and R

=== "Python"

``` bash
# keep data files in directory DATADIR out of the repo
DATADIR/  

# keep csv files everywhere  out of the repo
*.csv

# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
```

=== "R"

``` bash
# keep data files in directory DATADIR out of the repo
DATADIR/

# keep csv files everywhere  out of the repo
*.csv

# History files
.Rhistory
.Rapp.history

# Session Data files
.RData
.RDataTmp

# User-specific files
.Ruserdata

# Example code in package build process
*-Ex.R

# Output files from R CMD build
/*.tar.gz

# Output files from R CMD check
/*.Rcheck/

# RStudio files
.Rproj.user/

```

### Keep secrets and configuration out of version control

You also don't want to leak your AWS secret key or database username and password on Github.  Here's one way to do this:

- Store your secrets and config variables in a special file (for example called .env) in the root folder
- Add a line in `.gitignore` with the name of this special file. In this way this file will never get committed into the version control repository. 

### BOLD project .gitignore template

A preliminary .gitignore template has been created and is available [here](../files/agitignore.txt).
You can start with it and then edit it further to add other files/directories you want to make sure
that they are not commited in a code repo. This can also be included in the cookiekcutter template mentioned in the
[clear layout structure](3_clear_layout_structure.md) document

## pre-commit git hooks

![](img/precommithook.png)

Git hooks are scripts that Git executes before or after events such as: commit, push, and receive. Git hooks are a built-in feature - no need to download anything. Git hooks are run locally.

These hook scripts are only limited by a person's imagination. Some example hook scripts include:

pre-commit: Check the commit message for spelling errors.
pre-receive: Enforce project coding standards.
post-commit: Email/SMS team members of a new commit.
post-receive: Push the code to production.

We can use pre-commit git hooks by using pre-commit framework.The pre-commit framework bills itself 
as "A framework for managing and maintaining multi-language pre-commit hooks." Under the hood, it runs on python, 
but you can use the framework on any project, regardless of your project's primary language. You can install this by
typing `pip install pre-commit` on your console window


Once installed, you're going to add a pre-commit configuration file to your project root named `.pre-commit-config.yaml`. In that config file, you will need to specify which scripts pre-commit will run when your pre-commit hook is triggered by a git commit command.
There are plenty of ready made precommit hooks available [here](https://pre-commit.com/hooks.html). We will use some of them now
to tailor something useful for BOLD. This first example is suitable for Python code bases. A similar example with R will be provided soon.

We will add certain hooks to standardise the format of the code. We will also use black to make our code fully [PEP8](https://peps.python.org/pep-0008/) style guide compliant automatically.

The configuration file `.pre-commit-config.yaml` will look something like this :

```yaml 
   repos:
      - repo: https://github.com/pre-commit/pre-commit-hooks
        rev: v3.2.0
        hooks:
        - id: trailing-whitespace
        - id: end-of-file-fixer
        - id: check-added-large-files
        args: ['--maxkb=5000']
        description: do not upload files larger than 5000kb / 5MB to avoid data being uploaded
        - id: mixed-line-ending
        args: ['--fix=lf']
        description: Forces to replace line ending by the UNIX 'lf' character.
    -   repo: https://github.com/psf/black
        rev: 20.8b1
        hooks:
        - id: black
```

After creating `.pre-commit-config.yaml`  we can install it by typing  `pre-commit install` into the root folder where the config file is.
If everything has been done correctly a message saying `pre-commit installed at .git/hooks/pre-commit` will appear.
