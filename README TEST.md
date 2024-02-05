# COMP2913-SoftwareEngineeringProject
Welcome :)
## Contributing
Helpful rules to follow when contributing as a group
- Don't push code directly to main
### Setup
git config --global user.name "{USERNAME}"
git config --global user.email {EMAIL}
git config --global init.defaultBranch main
#### SSH
##### Unix
ssh-keygen -t ed25519 -C "{EMAIL}"
- pls check is same as account email
cat ~/.ssh/id.ed25519.pub
- copy the output and use as ssh key
##### Windows / Legacy
ssh-keygen -t rsa -b 4096 -C "{EMAIL}"
#### Connect repo
git init
git remote add origin {SSH OF THIS REPO}
git pull origin main
### Git Commands
| Reason | Command |
| ---- | ---- |
| check status | git status |
| update files from server | git pull origin {BRANCH} |
| add files to track | git add {FILES (use a . for "all"} |
| commit files | git commit -m "{MESSAGE}" |
| push files | git push origin {BRANCH} |
| move to a branch | git checkout {BRANCH} |
| move to a new branch | git checkout -b {BRANCH} |
| check branches | git branch |
| merge other branch into current one | git merge {BRANCH} |
| delete local branch | git branch -d {BRANCH} |
| delete branch  on server | git push origin --delete {BRANCH} |
#### Solving Merge Conflicts
- When working with remote you get a merge conflict 
- To solve open problem file and navigate to the chevrons where the error is:
```txt
...
<<<<<<< HEAD
HEAD CODE
=======
BRANCH CODE
>>>>>>> branch-{NAME}
...
```
- Remove the chevrons and either choose which part to use or write new code in it's place
- add, commit and then you can push the file with no conflict error