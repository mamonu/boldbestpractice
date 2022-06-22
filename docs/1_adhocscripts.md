

## Messy unorganised code 

Everyone starts somewhere. This is usually every project in the beginning. 
Trying something out with perhaps hardcoded minimal inputs and outputs.


• Code may not be well named or organised:

    Project1.r  
    lastworkingcodeFINALFINAL.R 
    ITWORKKKSSSS.R


Certainly this is not work that will be ready for sharing! Hopwfully by following the next steps in the BOLD Best Practices Manifesto an
analyst will have some ideas on many factors that can be improved and all together create a project that is easy to collaborate with that is
also reusable and reproducible.


## Can we do better?


There are some ways that even in this stage work can be useful.

An analyst can work in an exploratory mode, investigating processes and building familiarity with the problem domain. 
Usually work in this step is comprised of single file/ page programs that are in one file also known as `scripts` 

- [x] the focus on this step should be on learning and reducing uncertainties. Its an important first step on learning how to automate processes via programming and not doing things by hand / manually. 

Just be aware that there are better ways of organising this adhoc code. In this document hopefully we can signpost some of them



## Why someone should start to use Jupyter Notebooks?

By using technologies such as Jupyter notebooks (in Python/R)  an analyst explain how a process works to other people or him/herself after 6 months (!).Jupyter notebooks provide a quick and streamlined way for problem-solvers to prototype code and quickly share code. So in order to get started.

In a way, Jupyter notebooks strike a balance between simple text editors, which are fast to start and simple and easy to manipulate, and `IDE`'s (an acronym for "Integrated Development Environment") which tend to start slower and be feature-rich and complex. Simple text editors typically can only edit code, and cannot run the code. A full `IDE` can edit code, run the code, debug code, provide syntax highlighting and context help. In the context of problem-solving, Jupyter notebooks are quite handy. Jupyter notebooks open quickly and quickly produce output. Data exploration, data cleaning, and plot building are accomplished in Jupyter notebooks easier and quicker than in a text editor or an IDE.

## Why someone should not work ONLY with Jupyter Notebooks and work with an IDE

Jupyer notebooks are great for telling data stories. But, unless we are doing pure research, our research is the means to an end — and that is, getting valuable insights from our data stories and data models.

A production-grade pipeline needs to be composed out of debuggable, reproducible, easy-to-deploy, high-performance code components that could be orchestrated and scheduled. In its default version, it’s everything adhoc code on Jupyter isn’t.


## Next Steps


While just getting something to work in order to prove a point is good as far as running an adhoc program is concerned, 
in order to become more efficient it is good practice to not have repeating code. 

A way of not having parts of code being written again and again many times is to learn about functions and use them. These are covered in section [2](2_reusable_code.md)
