# git learning process

## initialize a directory as a repository

first,`mkdir dir` to make a directory
second,`cd dir` and then **`git init`**

`touch README.md` to cread a file named README.md

## add a file to current branch

**`git add README.md`**

multiple files is supported:

*`git add file1.c file2.py`*
## commit changes

**`git commit -m "some comment words"`**

## check the repository's status

**`git status`**

to check if any change has been made yet not commited

**`git diff`** to see what the changes are

## the change log(time line)

**`git log`**

optional arguement: `--pretty=oneline`

## roll back to old versions

git use `HEAD` to indicate the current vertion, which is the latest commited one, and `HEAD^` means the last vertion, `HEAD^^`,`HEAD^^^`...and so on, the shortcut for `HEAD^^^` is `HEAD~3`

**`git reset --hard HEAD^`** to roll back to last commit 