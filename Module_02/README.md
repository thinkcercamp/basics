# Git & Github

### <u>Dependencis</u>

Before learning about Git, you'll need ot install some dependencies.

**Install Xcode**

1) Please, please, please do this before the lesson. Everything else takes under a minute, but this step takes awhile to run.

https://developer.apple.com/xcode/

**Open a Terminal**

2) You'll be running the following commands in the terminal. You should have covered installing/adding in the module on command line and bash in Module 0. If you didn't, there is a terminal application that comes pre-installed on Macs which works fine, but I highly recommend this terminal replacement:

https://www.iterm2.com/

Note: You can run the following commands from any directory.

**Install Homebrew**

https://brew.sh/

3) Run the following command  to install:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

4) Run the following command to confirm isntallations:

```
which brew
```

That should return something similar to:

```
/usr/local/bin/brew
```



**Install Git**

5) To install:

```
brew install git
```

6) To confirm installation:

```
git --version
```

7) Which should return something like:

```
git version 2.17.0
```



**Setup an Account on Github**

8) Note, you may want to use a non ThinkCERCA email for this account. If you continue to code, Github will serve as a portfolio of your work and skills.

https://github.com/join



### <u>Now on to the Lesson</u>

### What is Version Control?

Semantic version control is a way of collaborating on code. Its also managing the history of change in your code base. Its very much like the version history in Google docs, except, in addition to being able to see a history of changes, who made them, and a snapshot of previous states, you can have different branches of history. 

Imagine you have a Google doc named, "Website Copy - Master". You and Collaborator A makes some changes to a google doc. Then, you duplicate that doc. You name the duplicate "Website Copy - New Call to Action".  Now, you and Collaborator B start making changes to the duplicate while Collaborator A ccontinues to work on the original. They both share a history of changes up to the point wher you duplicated it. All the changes after that are different and show different snapshots of that same doc. At some point down the line, you'll probably want to merge the work in your duplicate back into the master branch. Google docs doesn't have a way to do this, but Git does, and we'll get into it later.



**Further Reading on Version Control and Git**

https://www.atlassian.com/git/tutorials/what-is-version-control

https://www.atlassian.com/git/tutorials/what-is-git



### Git vs Github

Git is a version control software.

Github is a cloud storage service for Git repositories.



### Connecting Your Github Account to Your Local Installation of Git and Setting a Default Editor

1) You'll run the following commands to edit your local git configuration. You'll use youre Github handle and email. Here I've used mine as an example:

```bash
git config --global user.name "zan-rosenthal"
git config --global user.email zan.rosenthal@gmail.com
```

2) Now, set your default editor for git. This will allow you to write messages in your git history:

```bash
git config --global core.editor "code --wait"
```





###Starting a Repo

A repo, or repository is an object that contains all versions of a specific codebase. Going back to the Google Docs model, the repository is like a folder where all the different copies of the a single document live. However, instead of keeping every copy of the codebase on your computer, Git manages snapshots or commits. You can use git commands to check out any commit in your git history, which will instantly change the code you have on your computer to look like it did at the point of that commit. 



1)In the terminal, navigate to the top level directory of the portfolio project you started in Module 1f

2) Then type the following command:

```bash
git init
```

This will create a git repo in your current directory. Now we can start tracking changes.



**Making Your First Commit**

3) Make a change in your project. Next run:

```bash
git status
```

This will show the names for the files that have been modified. Git is watching all changes in this directory. 

4) Try:

```bash
git diff
```

This will show the contents of the file that have been changed and outline the delta, or changes, in the file. 

5) Now run:

```bash
git add [path to file]
git status
```

You'll noticed the color of the file name has changed. By running `git add` you've staged the files for commit. This means when we make a commit, those staged files will be included in the snapshot represented by that commit. Now we'll commit them and add the current snapshot of the directory to our git history. 

Note: If you want to add every file in your current directory you can run `git add .`

6) Run:

```bash
git commit
```

This should open your editor to allow you write a message describing the commit. Git commit messages should be short and descriptive and should use action verbs. For instance:

```
Add new border to About Us page footer
```

7) Once you've written your message in the file opened by git, save and close it. Then run:

```bash
git log
```

This will show you a history of commits. There are lots of ways to format this log to get the information you want.

8) Try running: 

```bash
git log --oneline
```

And notice the difference between that and the original log. Below is a link for the different formats you can use. Depending on the size of the project and number of collaborators, you may want different information in your git commits:

https://git-scm.com/docs/pretty-formats



### Making a New Branch

Now we'll add a new branch to our Git repo. Branches represent different Git histories that exist in the same repo. When collaborating with other developers, you'll usually each be working on different branches, each one tracking the changes made in your current work. When your finished, you'll merge your work back into a master branch, usually called `master`. 

1) Run

```bash
git branch new_branch
```

2) Make some changes to your project

3) Stage and commit those changes.

4) Now run

```bash
git log --graph --simplify-by-decoration --all
```

You'll see a visual structure that shows where your new branch branches off of master and has one commit on the new branch.

5) Run

```bash
git log
```

You should see your commit on this branch as well as your first commit

6) Run

```bash
git checkout master
git log
```

After you checking out to master, and running `log` again, you'll notice the commit from your new branch isn't there. That's becuase that commit is not included in the history on the `master` branch yet.



### Merging Changes

Now we'll merge your other branch into master.

1) While checked out to the `master` branch, run

```bash
 git merge new_branch
 git log
```

Now you'll see both commits represented in the master branch history.



###Pushing Your Commit to Github

Now, lets push this code to Github so other developers can collaborate with us on it.

1) Go to your Github account. 

2) Click on "Repositories". 

3) Click on New. 

4) Give your repo a name. 

​	- Its easiest to use the name of the directory where your git repository exists on your computer.  

5) Once created, copy the URL for the repo.

6) Return to your terminal and run:

```bash
git remote add origin [your repo url]
```

7) Now run:

```bash
git push origin master
```

8) Now if you can visit the repo you started on Github and you should see the commits you've made locally.



### Publishing Your Project to Github Pages

Note: You'll need a file called `index.html` as the starting point for your project in order for Github pages to be able to find it. There are different ways to configure it, but these instructions will assume that you have such a file with some html in it.

1) Go to the repo you created above on Github

2) Click the "Settings" tab at the top right of the main page of the repo

3) Scrioll down to the Github Pages section

4) In the source dropdown, select your `master` branch and click save.

5) Now you can visit **http://username.github.io/repository** and you should see your project. Sometimes it can take a few minutes to pick up on changes, so if its not there immediately, check back in a few minutes. 



You can find more detailed instructions here:

https://pages.github.com/



### Further Learning

Here is an interactive tutorial if you want to continue solidfying and extending the git knowledge you've begun to build here:

https://www.codecademy.com/learn/learn-git