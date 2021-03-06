# How to use Github

## Git & GitHub Resources
[Markdown language cheetsheet](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)  
[Git branches explanation](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)  
[Writing on Github](https://docs.github.com/en/free-pro-team@latest/github/writing-on-github)  
[Keys to a well witten readme](https://medium.com/chingu/keys-to-a-well-written-readme-55c53d34fe6d)  

## Brad Traversy's Guide of Git & GitHub
[youtube link](https://www.youtube.com/watch?v=SWYqp7iY_Tc)
commands
```
git init
git config --global user.name 'Brad Traversy'
git config --global user.email 'me@bradtraversy.com'
git add index.html
git status
git rm --cached index.html    //remove
git add *.html    // all the html file
git add .   //all the files
git commit    //vim editor be opened 
git commit -m 'Changed app.jus'
touch .gitignore     //Just write filename and prevent the file to go to staging area.
```
.gitignore
```
log.txt
/dir2
```
commands
```
git branch login
git chechout login    // Switch the branch
touch login.html
git add .
git commit -m "login form"
git checkout master
# The login.html file is gone, because you are in master branch, not in login branch!
git merge login
git remote add origin https://github.com/bradtraversy/myappsample.git
git remote   // See the remote repos
git push -u origin master
touch README.md
git add .
git commit -m "Added readme"
git push

git pull  //up-to-date

git branch -d <branch name> //delete a branch

//It lists the shortnames of each remote handle you’ve specified
git remote -v //See the connected repo

git remote add {shortName} {url} //Change the connected repo
git remote add origin git@github.com:sammy/my-new-project.git // origin is the default name git gives to a remote server

git push --mirror https://github.com/exampleuser/new-repository.git  // Duplicate
git remote set-url --push origin https://github.com/exampleuser/mirrored  // Change remote repository
// Update mirror
git fetch -p origin
git push --mirror

//git remote
git remote rm {name} //delete remote url

git push --all origin // all the branches at the same time to push

//git branch
git fetch --all //try this before git checkout --track origin/{branchname}
git checkout -t origin/test  //get remote branch origin/test if there is no test branch on local machine.
git reset --hard  //discard local changes
git checkout {filename}  //discard specific local changes

git reset {filename} //remove file from staging area
git checkout -- {filename} // do not commit which is not on the staging area

// discard unstaged file changes
git stash save --keep-index --include-untracked
git stash drop
```






# Problems
## .git file does not show up in VSCode
.git file is not showed in the vscode explorer. To solve this problem,
1. vscode menu -> Preference -> Setting
2. Search "files.exclude" which decides what types of files do not show.
3. Delete /.git

## Cannot make by "git branch login"
That is because git's master branch has not been made yet until you firstly commit your repo.
What you need to do is first commit! -> [stackoverflow's answer](https://stackoverflow.com/questions/9162271/fatal-not-a-valid-object-name-master/9162347)

## Non-related repos' merge method
```
fatal: refusing to merge unrelated histories
```
That would be happened when you try to merge unrelated repositories.
Use the option --allow-unrelated repositories.
```
git pull origin master --allow-unrelated-histories
```

[Solution url](https://www.educative.io/edpresso/the-fatal-refusing-to-merge-unrelated-histories-git-error)

## Branch error
Error message like this.
```
git checkout {branch name}

// return "fatal: unknown index entry format 0x18610000"
```
It was due to ./git/index file was broken. So delete and reset this file.
```
del .git/index
git reset
```

## Git clone with changed name folder
```
git clone {url} {name}
```









