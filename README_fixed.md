# Lab 2 - Git Commands

![911 GT2 RS](assets/manhart-tr-700-ii-3840x2160-19774.jpg)

## 1. Initialize the Repository

```bash
git init
git add .
git commit -m "first commit"

git remote add origin git@github.com:basel7ayman/Lab2.git
git push -u origin main
```

## 2. Create and Switch Between Branches

```bash
git branch dev
git branch test

git switch dev
git commit -am "add x to dev branch"
git commit -am "y added to dev"

git switch test
git commit -m "added a to test branch"
git commit -m "added b to test branch"
```

## 3. Merge `test` into `dev`

```bash
git switch dev
git merge --no-ff test
```

Resolve any merge conflicts, then complete the merge commit if Git asks you to.

## 4. View the Commit History

```bash
git log --oneline --graph
```

Example output:

```text
*   0dd8012 (HEAD -> dev) Merge branch 'test' into dev
|\
| * c126d33 (test) added b to test branch
| * af46887 added a to test branch
* | 6ab40a5 y added to dev
* | bb4c515 add x to dev
|/
* 0539633 (origin/main, main) first commit
```

## 5. Merge `dev` into `main` and Push Branches

```bash
git switch main
git merge dev

git push -u origin main
git push -u origin dev
git push -u origin test
```

## 6. Delete Branches

Delete the local branches:

```bash
git branch -d test
git branch -d dev
```

Delete the remote branches:

```bash
git push origin --delete test
git push origin --delete dev
```

## 7. Stash Changes

```bash
git switch -c basel
git add .
git stash
git stash list

git switch main
git switch basel
git stash pop
```

## 8. Create and Delete a Tag

Create and push the tag:

```bash
git tag -a v1.7 -m "version 1.7"
git push --tags
git tag
```

Delete the local and remote tag:

```bash
git tag -d v1.7
git push origin --delete v1.7
```
