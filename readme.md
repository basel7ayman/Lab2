git init
git add .
git commit -m "first commit"

git remote add origin git@github.com:basel7ayman/Lab2.git
git push -u origin main

git branch dev
git branch test

git switch dev
git commit -am "add x to dev branch"
git commit -am "y added to dev"

git switch test
git commit -m "added a to test branch"
git commit -m "added b to test branch"

git switch dev
git merge --no-ff test // resolved conflict
(Merge branch 'test' into dev)

git log --oneline --graph
*   0dd8012 (HEAD -> dev) Merge branch 'test' into dev
|\  
| * c126d33 (test) added b to test branch
| * af46887 added a to test branch
* | 6ab40a5 y added to dev
* | bb4c515 add x to dev branch
|/  
* 0539633 (origin/main, main) first commit

git switch main
git merge dev

git push -u origin main
git push -u origin dev
git push -u origin test

git branch -d test
git branch -d dev
git push origin --delete test
git push origin --delete dev

git switch -c basel
git add .
git stash
git stash list
git switch main
git switch basel
git stash pop

git tag -a v1.7 -m "version 1.7"
git push --tags
git tag
git tag -d v1.7
git push origin --delete v1.7

![manhart-tr-700-ii-3840x2160-19774](assests\manhart-tr-700-ii-3840x2160-19774.jpg)