## One idea one commit
https://secure.phabricator.com/book/phabflavor/article/recommendations_on_revision_control/

### Workflow
http://thomas-barthelemy.github.io/2015/08/20/phabricator-arcanist-flow/
1. Pull master's current code
2. Use `arc branch B` to create a local branch
3. Code your changes and use `arc diff` to diff your code
4. Checkout master again and pull the current code
5. Use `arc branch SB` to create a local branch
6. Code your changes and use `arc diff` to diff your code

http://verraes.net/2013/10/pre-merge-code-reviews/
