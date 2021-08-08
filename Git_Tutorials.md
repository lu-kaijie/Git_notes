# 1.Git流程图
![image of git](https://user-images.githubusercontent.com/81409445/128616993-b3ccbd72-d22c-46b9-9c9d-ae55be966826.png)
* **工作区、暂存区、本地仓库都是在自己电脑上完成**
* **远程仓库如github上的仓库**
# 2.Git常用命令
Git中所有命令都是以`git`开头,如上图中的`git add`、`git commit`、`git push`、`git pull`、`git clone`等主要命令。  
为方便演示，以我为例，在`D`盘的`CoderLife`文件夹下创建`demo`的子文件夹，在其中新建一个名为`git_learn.txt`的文本文件。
第二节Git常用命令演示都是基于此`demo`文件夹  
![image](https://user-images.githubusercontent.com/81409445/128617659-5a644198-4a58-4679-a9e6-f4d3b8e913ad.png)  
在`CoderLife`目录下点击右键在选择 Git Bash Here，打开Git Bash窗口，在命令行中输入 `cd demo`转到`demo`子目录下，也可以直接鼠标点击`demo`进入再打开Git Bash啦。  
![image](https://user-images.githubusercontent.com/81409445/128617859-966dcdae-ff38-439c-8246-a958801935ae.png)  
## 2.1 git status
`git status`顾名思义，查看仓库状态，对于像我这样的新手来说，最常用的命令了属于是。建议读者多用此命令，以免出错。  
在命令行中输入`git status`，显示不是一个git仓库，现在当然不是了，因为我们还没有执行相关命令。
![image](https://user-images.githubusercontent.com/81409445/128618021-e38d78be-cb20-4c16-b80c-c954c4ae0ad2.png)
## 2.2 git init
`git init`初始化一个Git仓库，也就是上文提到的命令，输入此命令，如图，此时`demo`已经初始化为一个git仓库了。也可以在`CoderLife`下执行`git init demo`也是一样的效果。  
![image](https://user-images.githubusercontent.com/81409445/128618401-dcc6f9c8-e614-4ec4-ae05-544da93513f7.png)  
注意到结果显示初始化了一个空仓库，虽然我们在`demo`下有个`git_learn`文件，但我们并没有把他加入本地仓库，所以显示为空仓库。  
而且还出现了`（master）`字样，`master`是Git仓库创建的一个默认主分支。  
为了更直观，我们可以通过`git status`查看此时仓库状态。此时显示在分支`master`上，还没有commit，也就是说有东西没上传，且有一个未追踪文件`git_learn.txt`。可以使用`git add`命令来上传。
## 2.3 git add
在命令行输入`git add git_learn.txt`，使用`git status`查看此时仓库状态，显示在分支`master`上，还没有commit，也就是还是有没东西上传，但有一个新文件，
`git add`命令把这个新文件传入了暂存区，也就是缓冲区。  
![image](https://user-images.githubusercontent.com/81409445/128618591-a7dafa76-4061-4ab9-b139-63e5252b543b.png)
## 2.4 git commit -m '注释内容'
接下来输入`git commit -m 'the first commit'`,把刚才`add`到缓冲区的文件上传到本地仓库，`-m`表示给上传的文件添加引号内的注释，
通过`git status`查看此时仓库状态`nothing to commit, working tree clean`表示上传完成，没有东西需要上传了。

![image](https://user-images.githubusercontent.com/81409445/128618902-a0ff6943-dcf0-46e6-8b05-a3fe0126550d.png)
## 2.5 git log
输入`git log`查看仓库提交日志，显示了作者、时间和提交信息

![image](https://user-images.githubusercontent.com/81409445/128619032-7c570d91-82f9-446c-9699-b420ac6f8ba7.png)
## 2.6 git branch
* `git branch`显示当前仓库的分支，如图此时我们只有master一个分支，`*master`表示我们此时处于master分支
* `git branch a`表示创建一个名为`a`的分支。**考虑可读性，建议取名有意义，以免自己弄混**

![image](https://user-images.githubusercontent.com/81409445/128619193-595d0683-d150-498d-a799-184f9b7b893d.png)
## 2.7 git checkout
再次输入`git branch`查看当前分支，输出显示已经有`master`和`a`两个分支了，输入`git checkout a`切换到`a`分支  
![image](https://user-images.githubusercontent.com/81409445/128620087-42dcb5b7-a936-450a-b487-d97baf91c02d.png)
# 3.通过Git将文件传到Github
下面通过几个实例来学习git命令


