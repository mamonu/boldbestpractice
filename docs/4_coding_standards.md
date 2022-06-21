# 4 Coding standards 

## Sensible defaults

This section sets out sensible defaults which you are recommended to follow. They are not strict rules, but are recommended  
=== "Python"


- [x] Be aware of the Python Style guide also known as [PEP8](https://peps.python.org/pep-0008/) .You can use the [black](https://black.readthedocs.io/en/stable/) formatter so that your code can follow PEP8 automatically.
- [x] Use Python 3 instead of Python 2. Use versions of Python that have security support and will be supported for a while. At the moment of writing 3.8 is the recommended version but this can change with time. Consult [this](https://endoflife.date/python) page to see when security support ends for different versions
- [x] Use pandas for data analysis on smaller datasets. Pyspark for bigger datasets

=== "R"


- [x] Follow the [Tidyverse Style Guide](https://style.tidyverse.org/index.html)
- [x] Default to packages from the Tidyverse, because they have been carefully designed to work together 
  effectively as part of a modern data analysis workflow. 
  
  More info can be found here: [R for Data Science by Hadley Wickham](https://r4ds.had.co.nz). 
  

## Naming conventions

Use meaningful names - well-named functions and variables can remove the need for a comment and make life a 
little easier for other readers, including your future self. 
Avoid meaningless names like ‘obj’ / ‘result’ / ‘foo’.
Don’t be cute or jokey when naming things.
Use single-letter variables only where the letter represents a well-known mathematical property (e.g. e = mc^2), or where their meaning is otherwise clear.

## Clear and concise code

Choose clarity over cleverness - use advanced language tricks with care.
Less code is usually better - but not at the expense of clarity.
Use code comments well (see above).

## Linters

A linter is a tool that analyses code to check for programmatic and stylistic errors. You should apply a linter to review your code formatting, which will mean your coding style will be consistent across projects and make it easier for others to understand.

In RStudio, the keyboard shortcut ‘ctrl+shift+A’ will reformat your code and automate some of the process of passing the linter. If you apply the linter as you work, rather than at the end, you will find it much easier to write code that passes the linter first time.

For R use Lintr and follow the [Tidyverse Style Guide](https://style.tidyverse.org/index.html).
For Python, use [black](https://github.com/psf/black) and follow [PEP8](https://peps.python.org/pep-0008/).
If possible, set up your linters to run automatically on all pull requests, using Github Actions.

## Error messages
Errors will occur, so write your error messages in a way that provide useful information to end users and people working on the code.

## Encoding and CSVs	

Use unicode for character encoding. This means you should convert inputs that include non-ASCII characters to unicode as early as possible in your data processing workflow. If you are outputting to text files, these should be encoded in `utf-8`.
