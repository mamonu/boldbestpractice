# 4 Version control



## Motivation and Background

Version control helps us understand what changes we made in the past or why we did a specific analysis in the way we did it, even weeks or months later. With the help of comments and commit messages, each version can explain what changes it contains compared to the previous versions. 
This is helpful in order to be able to share our analysis  and make it auditable or reproducible - which is good scientific practice.

A version control system neatly stores a history of changes and who made them, so while it is still easy to access them, your working directory is not cluttered by the debris of previous versions that are necessary to keep just in case. Similarly, with version control, there is no need to leave chunks of code commented should you ever need to come back to an old version again.

Finally, version control is invaluable for collaborative projects where different people work on the same code simultaneously and build on each other’s work. It allows the changes made by different people to be tracked and can automatically combine people’s work while saving a great deal of painstaking effort to do so manually. Using version control for your research project means that your work is totally transparent, and because all your actions are recorded, it enables others to reproduce your studies. Moreover, version control hosting services such as GitHub provide a way to communicate and collaborate in a more structured way, such as in pull requests, code reviews, and issues.

Version control is a systematic approach to record changes made in a file, or set of files, over time. This allows you and your collaborators to track the history, see what changed, and recall specific versions later when needed. A typical procedure for using version control is as follows:

- [x] Create files - these may contain text, code or both.
- [x] Work on these files, by changing, deleting or adding new content.
- [x] Create a snapshot of the file status (also known as version) at this time.



This process of creating a snapshot is described as a “commit”. As you keep saving your work by adding changes, you make more and more snapshots. 
You can think of these as saving versions of these files while documenting their history. If you need to go back to a previous version of a file because of a mistake, or if you changed your mind about a previous update, you can access the file in your preferred version, or return your entire project to a past state.

![](https://github.com/mamonu/boldbestpractice/raw/main/docs/img/gitcommits.png)


## Non-Linear Development of Your Project with “Branches”


So you have your project and you want to add something new or try something out before reflecting the changes in the main project folder. To add something new, you can continue editing your files and save them with the proposed changes. Suppose you want to try something without reflecting the changes in the central repository. In that case, you can use the “branching” feature of more advanced version control systems such as Git. A branch creates a local copy of the main repository where you can work and try new changes. Any work you do on your branch will not be reflected on your main project (referred to as your main branch) so it remains secure and error-free. At the same time, you can test your ideas and troubleshoot in a local branch.

![](https://github.com/mamonu/boldbestpractice/raw/main/docs/img/git-graph.png)

When you are happy with the new changes, you can introduce them to the main project. The merge feature in Git allows the independent lines of development in a local branch to get integrated into the main branch.



## General Proposed Workflow

- [x] Make your project version controlled by initialising a Git repository in its directory using `git init` 

- [x] Add and commit all your files to the repository using `git add .` then `git commit` 

- [x] Continue to add and commit changes as your project progresses. Stage the changes in specific files to be committed with `git add <FILES> ` , and add messages to your commits.

- [x] Each commit preferably should make one simple change. Commit messages are meaningful, with a ~50 character summary at the top. Commit messages are in the present tense and imperative.

- [x] Develop new features on their own branches, which you can create via `git checkout -b <MYNEWBRANCH>` and switch between via `git checkout < MYNEWBRANCH >` 

- [x] Make sure branches have informative names.

- [x] Make sure the main branch is kept clean.

- [x] Make sure each branch has a single purpose and only changes related to that purpose are made on it.

- [x] Once work on a branch  is complete, it is recommended that a Pull Request is sent for review 




``` bash title="example git command sequence"
git pull #for the latest in the repo you want
git checkout -b MYNEWBRANCH #or any other name to start your own

# code writing  here 
git add FILES  
git commit -m "commit message here"

# more code writing here 
git add FILES 
git commit -m "commit message here"

# even more code writing  
git add FILES 
git commit -m "commit message here"

git push -u origin MYNEWBRANCH

# got to github repo at branch MYNEWBRANCH
# PULL REQUEST from Github Interface
```


## Code review

Code review provides additional assurance that code logic is correct, as well as providing feedback on code and problem structuring. For smaller projects, the review only needs to be a simple read-through and sanity check.

Code reviews should be initiated through the creation of a pull request. The review should typically involve the reviewer pulling the code to their local machine, testing it, and leaving comments in the pull request.

Remember that it’s always easier (for both you and your reviewers) if you commit and push your changes regularly. You should merge branches into the master regularly so that reviewers review little and often, rather than attempting to review your entire codebase all at once.






*[MYNEWBRANCH] : Put your branch name here!
*[FILES] : Put your file name/names here!
