# 3 Coding standards 


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

For R use Lintr and follow the Tidyverse Style Guide.
For Python, use black and follow PEP8.
If possible, set up your linters to run automatically on all pull requests, using Github Actions.

## Error messages
Errors will occur, so write your error messages in a way that provide useful information to end users and people working on the code.
