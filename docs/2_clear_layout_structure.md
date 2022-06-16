# 2 Use a clear layout structure

The next step above doing adhoc exploratory work is to use the directory hierarchy to organise the project

## Use directory hierarchy


- Some proposed suggestions are to have a README file at the root of the project where a user can find out more 
about the project in hand. Perhaps also the set of commands needed to run an analysis script.

- There should be separate directories for the analysis inputs, code itself & the outputs. This will also help at a later point as it will make data breaches less likely.

 - There needs to be a separate directory for ‘ad hoc’ exploratory code/notebooks like the ones discussed that are probably so that they don’t interfere in anyway with the main code.


## Use meaningful folder/file names 

A very detailed example of how a project could look (example for a Python project)
```
├── LICENSE
├── README.md          <- The top-level README
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs              
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── adhocnotebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- Make this project pip installable with `pip install -e`
├── src                <- Source code for use in this project.
    ├── __init__.py    <- Makes src a Python module
    │
    ├── data           <- Scripts to download or generate data
    │   └── make_dataset.py
    │
    ├── features       <- Scripts to turn raw data into features for modeling
    │   └── build_features.py
    │
    ├── models         <- Scripts to train models and then use trained models to make
    │   │                 predictions
    │   ├── predict_model.py
    │   └── train_model.py
    │
    └── visualization  <- Scripts to create exploratory and results oriented visualizations
        └── visualize.py
```


There is a project that creates a folder structure example: COOKIECUTTER 
https://drivendata.github.io/cookiecutter-data-science/
No need to be as thorough though.

Similar for R: projecttemplate

http://projecttemplate.net/index.html
