# 3 Use a clear layout structure

The next step above doing adhoc exploratory work is to use the directory hierarchy to organise the project

## Use directory hierarchy


- Some proposed suggestions are to have a README file at the root of the project where a user can find out more 
about the project in hand. Perhaps also the set of commands needed to run an analysis script.

- There should be separate directories for the analysis inputs, code itself & the outputs. This will also help at a later point as it will make data breaches less likely.

 - There needs to be a separate directory for ‘ad hoc’ exploratory code/notebooks like the ones discussed that are probably so that they don’t interfere in anyway with the main code.


## Use meaningful folder/file names 

A well-defined, standard project structure means that a newcomer can begin to understand an analysis without digging in to extensive documentation. It also means that they don't necessarily have to read 100% of the code before knowing where to look for very specific things.

Well organized code tends to be self-documenting in that the organization itself provides context for your code without much overhead. People will thank you for this because they can:

Collaborate more easily with you on this analysis
Learn from your analysis about the process and the domain
Feel confident in the conclusions at which the analysis arrives

A very detailed example of how a project could look (example for a Python project)
```
├── LICENSE
├── .gitignore     <- files that should not be commited to a repo
├── README.md      <- The top-level README
├── data
│   ├── external   <- Data from third party sources.
│   ├── interim    <- Intermediate data that has been transformed.
│   ├── processed  <- The final, canonical data sets for modeling.
│   └── raw        <- The original, immutable data dump.
│
├── docs              
│
├── models          <- Trained and serialized models,model predictions,or model summaries
│
├── adhocnotebooks  <- Jupyter notebooks. Naming convention is a number (for ordering),
│                      the creator's initials, and a short `-` delimited description, 
│                      e.g. 1.0-jqp-initial-data-exploration`.
│
├── references      <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports         <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures     <- Generated graphics and figures to be used in reporting
│
├── src             <- Source code for use in this project.
    ├── __init__.py <- Makes src a Python module if needed
    │
    ├── data        <- Scripts to download or generate data
    │   └── make_dataset.py
    │
    ├── features    <- Scripts to turn raw data into features for modeling
    │   └── build_features.py
    │
    ├── models      <- Scripts to train models and then use trained models to make
    │   │                 predictions
    │   ├── predict_model.py
    │   └── train_model.py
    │
    └── visualization <- Scripts to create exploratory and results oriented visualizations
        └── visualize.py
```


### Proposed Python helper

There is a project that creates a folder structure for python projects called [cookiecutter](https://cookiecutter.readthedocs.io/en/latest/)

A suggested BOLD solution is that we can create a BOLD cookiecutter template that every analyst can use by 
typing `cookiecutter BOLD-Template` and then can provide the agreed upon directories of a starting slate
We can agree on what will be needed in a discusion via the Github [Issues](https://github.com/mamonu/boldbestpractice/issues) interface

###  Proposed R helper
Similarly for R: [projecttemplate](http://projecttemplate.net/index.html)

`ProjectTemplate` is a system for automating the thoughtless parts of a data analysis project:

Curating the best R packages.
Providing simple tools for keeping a log of your work
Providing template code for:
- Data diagnostics
- Data munging
- Code profiling
- Unit testing

