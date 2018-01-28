# git-commands 

## git log  
### scroll on log pager
Git uses the command line pager, Less, to page through all of the information. The important keys for Less are:  

to scroll down by a line, use j or ↓  
to scroll up by a line, use k or ↑  
to scroll down by a page, use the spacebar or the Page Down button  
to scroll up by a page, use b or the Page Up button  
to quit, use q  

### git log --oneline
```
$ git log --oneline
```

This command:

⋅⋅* lists one commit per line
⋅⋅* shows the first 7 characters of the commit's SHA
⋅⋅* shows the commit's message
