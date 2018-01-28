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
