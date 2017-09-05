# git learning process

## initialize a directory as a repository

first,`mkdir dir` to make a directory
second,`cd dir` and then **`git init`**

`touch README.md` to cread a file named README.md

## add a file to current branch

**`git add README.md`**

**`git rm filename`** will remove a added file

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

## after roll back

**`git checkout -- filename`** equals to modify the file and `git add filename` again

>git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

# remote repository access

**`ssh-keygen -t rsa -C "youremail@example.com"`** to creat a ssh key first

**`git remote add origin git@github.com:Black-Web/learngit.git`** 

**`git push -u origin master`**

>把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。

>由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

after doing this, just**`git push origin master`** to push local changes to the remote server

## colone a remote repository

**`git clone git@github.com:Black-Web/hello-world.git`**

# branches management

## creat branch

**`git branch dev`** will craet new branch *dev*

**`git chechout dev`** switch from master to dev


>查看分支：git branch
>
>创建分支：git branch <name>
>
>切换分支：git checkout <name>
>
>创建+切换分支：git checkout -b <name>
>
>合并某分支到当前分支：git merge <name>
>
>删除分支：git branch -d <name>

`git merge <name>` can optionally followed by *--no-ff* 

>带 *--no-off* 参数的merge命令会自动执行一个commit，因此还需要带参数*-m "some comment"* , 执行完可以用 *git log* 查看merge记录

**`git log --graph`** to display the edit history graphically

## stash -- store the current working process

>修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；
>
>当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。

