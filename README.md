# git-commands 

## git log  
### scroll on log pager
Git uses the command line pager, Less, to page through all of the information. The important keys for Less are:  

- to scroll down by a line, use j or ↓  
- to scroll up by a line, use k or ↑  
- to scroll down by a page, use the spacebar or the Page Down button  
- to scroll up by a page, use b or the Page Up button  
- to quit, use q  

### git log --oneline
```
$ git log --oneline
```

This command:  

- lists one commit per line  
- shows the first 7 characters of the commit's SHA  
- shows the commit's message  

### git log --stat
To recap, the --stat flag is used to alter how git log displays information:
```
$ git log --stat
```

This command:

- displays the file(s) that have been modified
- displays the number of lines that have been added/removed
- displays a summary line with the total number of modified files and lines that have been added/removed  

### git log -p
To recap, the -p flag (which is the same as the --patch flag) is used to alter how git log displays information:
```
$ git log -p
```

This command adds the following to the default output:

- displays the files that have been modified
- displays the location of the lines that have been added/removed
- displays the actual changes that have been made

to display details for a specific commit:   
```
$ git log -p fdf5493
```

### Git Add  
The git add command is used to move files from the Working Directory to the Staging Index.  
```
$ git add <file1> <file2> … <fileN>  
```
This command:  

- takes a space-separated list of file names  
- alternatively, the period . can be used in place of a list of files to tell Git to add the current directory (and all nested files)  

### Git Commit  
The git commit command takes files from the Staging Index and saves them in the repository.  
```
$ git commit
```
This command:

- will open the code editor that is specified in your configuration
- (check out the Git configuration step from the first lesson to configure your editor)  
  
Inside the code editor:  
- a commit message must be supplied  
- lines that start with a # are comments and will not be recorded
- save the file after adding a commit message
- close the editor to make the commit

### Git Diff  
To recap, the git diff command is used to see changes that have been made but haven't been committed, yet:  
```
$ git diff
```
This command displays:  

- the files that have been modified
- the location of the lines that have been added/removed
- the actual changes that have been made

### Git Ignore  
To recap, the **.gitignore** file is used to tell Git about the files that Git should not track. This file should be placed in the same directory that the **.git** directory is in.  
Globbing lets you use special characters to match patterns/characters. In the .gitignore file, you can use the following:  

- blank lines can be used for spacing  
- **#** - marks line as a comment  
- __*__ - matches 0 or more characters  
- **?** - matches 1 character  
- **[abc]** - matches a, b, or c  
- __**__ - matches nested directories - __a/**/z__ matches:  
  - a/z  
  - a/b/z  
  - a/b/c/z  
  
### Git Tag Recap
To recap, the git tag command is used to add a marker on a specific commit. The tag does not move around as new commits are added.  
```
$ git tag -a beta
```
This command will:  

- add a tag to the most recent commit
- add a tag to a specific commit if a SHA is passed

### Git Branch
To recap, the git branch command is used to manage branches in Git:  
```
# to list all branches
$ git branch

# to create a new "footer-fix" branch
$ git branch footer-fix

# to delete the "footer-fix" branch
$ git branch -d footer-fix
```  
This command is used to:  

- list out local branches
- create new branches
- remove branches  

shortcut to create and move to new branch:  
``` 
$ git checkout -b amend-my-name
``` 

display all the history if a pseudo graphical way:
``` 
$ git log --oneline --decorate --graph --all
``` 

### Merge
To recap, the git merge command is used to combine branches in Git:  
``` 
$ git merge <other-branch>
``` 

There are two types of merges:  

- Fast-forward merge – the branch being merged in must be ahead of the checked out branch. The checked out branch's pointer will just be moved forward to point to the same commit as the other branch.  
- the regular type of merge
  - two divergent branches are combined
  - a merge commit is created

### Merge Conflict 

#### Merge Conflict Indicators Explanation
The editor has the following merge conflict indicators:

- __<<<<<<< HEAD__ everything below this line (until the next indicator) shows you what's on the current branch
- __||||||| merged common ancestors__ everything below this line (until the next indicator) shows you what the original lines were
- __=======__ is the end of the original lines, everything that follows (until the next indicator) is what's on the branch that's being merged in
- __>>>>>>> heading-update__ is the ending indicator of what's on the branch that's being merged in (in this case, the __heading-update__ branch)

A merge conflict happens when the same line or lines have been changed on different branches that are being merged. Git will pause mid-merge telling you that there is a conflict and will tell you in what file or files the conflict occurred. To resolve the conflict in a file:  

- locate and remove all lines with merge conflict indicators
- determine what to keep
- save the file(s)
- stage the file(s)
- make a commit

Be careful that a file might have merge conflicts in multiple parts of the file, so make sure you check the entire file for merge conflict indicators - a quick search for <<< should help you locate all of them.

### Revert 
To recap, the git revert command is used to reverse a previously made commit:
```
$ git revert <SHA-of-commit-to-revert>
```

### Reset 
To recap, the git reset command is used erase commits:
```
$ git reset <reference-to-commit>
```
It can be used to:

- move the HEAD and current branch pointer to the referenced commit
- erase commits with the --hard flag
- moves committed changes to the staging index with the --soft flag
- unstages committed changes --mixed flag  

Typically, ancestry references are used to indicate previous commits. The ancestry references are:   

- __^__ – indicates the parent commit
- __~__ – indicates the first parent commit

### Remote
```
$ git remote add repo-on-GitHub https://github.com/richardkalehoff/RichardsFantasticProject.git
```

A remote repository is a repository that's just like the one you're using but it's just stored at a different location. To manage a remote repository, use the git remote command:
```
$ git remote
```
- It's possible to have links to multiple different remote repositories.  
- A shortname is the name that's used to refer to a remote repository's location. Typically the location is a URL, but it could be a file path on the same computer.  
- git remote add is used to add a connection to a new remote repository.  
- git remote -v is used to see the details about a connection to a remote.  


