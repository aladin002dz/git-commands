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
