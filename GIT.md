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
3. Clone: `git clone <giturl> [foldername]`
4. History: `git log` & `git log --oneline`
5. Graph & GUI: `git log --oneline --graph` & `gitk`
6. 



