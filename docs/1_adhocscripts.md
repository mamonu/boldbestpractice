

## Messy unorganised code 

Everyone starts somewhere. This is usually every project in the beginning. 
Trying something out with perhaps hardcoded minimal inputs and outputs.


Also at this point code may not be well named or organised:

!!! danger
    examples of badly named filenames that do not explain what the code contained in the file is doing:
    ```
    Project1.r  
    lastworkingcodeFINALFINAL.R 
    ITWORKKKSSSS.py
    ```


Certainly this is not work that will be ready for sharing! Hopwfully by following the next steps in the BOLD Best Practices Manifesto an
analyst will have some ideas on many factors that can be improved and all together create a project that is easy to collaborate with that is
also reusable and reproducible.


## Can we do better?


There are some ways that even in this stage work can be useful.

An analyst can work in an exploratory mode, investigating processes and building familiarity with the problem domain. 
Usually work in this step is comprised of single file/ page programs that are in one file also known as `scripts` 

!!! info
    the focus on this step should be on learning and reducing uncertainties. 
    Its an important first step on learning how to automate processes via programming and 
    not doing things by hand / manually. 

Just be aware that there are better ways of organising this adhoc code. In this document hopefully we can signpost some of them.



## Why someone should start to use Jupyter Notebooks?

By using technologies such as Jupyter notebooks (in Python/R)  an analyst explain how a process works to other people or him/herself after 6 months (!).Jupyter notebooks provide a quick and streamlined way for problem-solvers to prototype code and quickly share code. So in order to get started.

In a way, Jupyter notebooks strike a balance between simple text editors, which are fast to start and simple and easy to manipulate, and `IDE`'s (an acronym for "Integrated Development Environment") which tend to start slower and be feature-rich and complex. Simple text editors typically can only edit code, and cannot run the code. A full `IDE` can edit code, run the code, debug code, provide syntax highlighting and context help. In the context of problem-solving, Jupyter notebooks are quite handy. Jupyter notebooks open quickly and quickly produce output. Data exploration, data cleaning, and plot building are accomplished in Jupyter notebooks easier and quicker than in a text editor or an IDE.

## Why someone should not work ONLY with Jupyter Notebooks and work with an IDE

Jupyer notebooks are great for telling data stories. But, unless we are doing pure research, our research is the means to an end — and that is, getting valuable insights from our data stories and data models.

A production-grade pipeline needs to be composed out of debuggable, reproducible, easy-to-deploy, high-performance code components that could be orchestrated and scheduled. In its default version, it’s everything adhoc code on Jupyter isn’t.

Out of 400 cells, could cell # 273 run even if cell #50 did not run? What if it did run, but on a different data, reading different data? Are cell #200’s results immutable? I.e. can we re-run it and get the same results, or will a re-run fail/return different results?

There is no easy way of answering any of those questions while developing on a Jupyter Notebook.

You have to rely on your human memory to know which cell could run with/without other cells, which cell is re-runnable, etc. 
This just doesn’t work. Basically, what most data scientists do when they are unsure about the state of a notebook, is just trigger a complete re-run of the entire notebook, which is a complete waste of time and resources.

Notebooks are useful tools for interactive data exploration which is the dominant activity of a data scientist working on the early phase of a new project or exploring a new technique. But once an approach has been settled on, the focus needs to shift to building a structured codebase around this approach while retaining some ability to experiment. The key is to build the ability to experiment into the pipeline itself. An example would be including a machine learning model registry which allows one to modify parameters at either run-time or build-time and stores results such as performance metrics in a data store. This has the advantage that experiments are always repeatable as they run with versioned code and their results are retained for purposes of comparison, and also as demonstrable markers of progress. 


## So what is the solution

For R the use of RStudio, a fully fledged IDE ("Integrated Development Environment").
For Python VSCode is recommended



## Next Steps


While just getting something to work in order to prove a point is good as far as running an adhoc program is concerned, 
in order to become more efficient it is good practice to not have repeating code. 

A way of not having parts of code being written again and again many times is to learn about functions and use them. These are covered in section [2](2_reusable_code.md)
