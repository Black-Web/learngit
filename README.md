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

**`git log`** will show the history of modification from the current vertion

optional arguement: `--pretty=oneline`

**`git reflog`** to display the whole time line, including the 'future' commited vertion, and show the *commit id*, which is useful to withdraw a roll back operation

## roll back to old versions

git use `HEAD` to indicate the current vertion, which is the latest commited one, and `HEAD^` means the last vertion, `HEAD^^`,`HEAD^^^`...and so on, the shortcut for `HEAD^^^` is `HEAD~3`

**`git reset --hard HEAD^`** to roll back to last commit

while `HEAD^` can be replaced by a *commit id* which indicate the last vertion

## a clearly stupid doc