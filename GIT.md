Git
----
# Setting up [Gerrit](https://www.gerritcodereview.com/) Code Review

## Setup ssh key
`cat ~/.ssh/id_rsa.pub`

`ssh-keygen -t rsa -C "email"`

## Forking from website

## Strategies 
1. Centralized: Mimics SVN, no local repository
2. Patched workflow: Common used in linux kernel, Original git workflow, Send patch file and pass around (email). Don't trust anyone, see the intention only.
3. Forked workflow: Fork -> Clone -> Checkout. Commit -> Push -> Pull Request.
4. Branching workflow: Create branches for each contributor. Trust contributor.

## Deployment
1. Scheduled (1 master, 1 development, several features, hotfixes, bug fixes branches). Using version as branch name / git flow. Example: Drupal.
2. Continuous (1 master & several feature branches). Everything is equally important. Rely heavily on automated testing/gatekeeper (series of gated checkin/testing suites). Example: Git

## Tips:
1. Use "resolves Issues #2" inside the commit message to automatically link issue with commit (also to change status of issue).

## Finding bugs
1. Bisect
2. 

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
13. Add remote repos: `git remote add <remote_name> <remote_repo_path_or_url>`
14. Show Branches (all & remotes): `git branch -a` & `git branch -r`
15. Update branches: `git fetch`
16. Checkout a branch: local: `git checkout <branch_name>` & remote with tracking: `git checkout --track <remote>/<branch_name>`. If only have 1 remote, no need to use remote name.
17. Create a new branch from existing branch: `git checkout -b <new_branch_name> <from_branch_name>`
18. Delete a branch `git branch -d <branch_name>`
19. Change commit message `git commit --amend`
20. Push commits & branch: `git push --set-upstream <remote> <branch>` & subsequent `git push`
21. Merge from: `git merge <branch_name>`
22. Difference between 2 points in history: Commits: `git log HEAD^` & Commits changes: `git diff HEAD^`
