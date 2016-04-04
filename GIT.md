Git
----

## Setup ssh key
`cat ~/.ssh/id_rsa.pub`

`ssh-keygen -t rsa -C "email"`

## Forking from website

## Strategies 
1. Centralized: Mimics SVN, no local repository
2. Patched workflow: Common used in linux kernel, Original git workflow, Send patch file and pass around (email). Don't trust anyone, see the intention only.
3. Forked workflow: Fork -> Clone -> Checkout. Commit -> Push -> Pull Request.
4. Branching workflow: Create branches for each contributor. Trust contributor.

## Commands
1. Version: `git --version`
2. Help: `git help all`
3. Clone: `git clone <giturl> [foldername]` | Clone from local repo: `git clone <git folder path> [foldername]` >> `git remote -v` show local remote
4. History: `git log` & `git log --oneline`
5. Graph & GUI: `git log --oneline --graph` & `gitk`
6. Config: `git config [--global|--local] user.email 'email.com'` 
7. Initialized a directory: `mkdir <project>`, `cd <project>`, & `git init`
8. Check untracked files: `git status`
9. Add untracked files `git add <file>` & `git add .`
10. Commit: `git commit [-m <comment>]`
11. Show remote repos: `git remote` & `git remote -v` 
12. Copying snapshot just by `cp <cloned_repo> <new_repo>` include remote
13. 

