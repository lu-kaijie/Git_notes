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
## 3.1实例1 ：把本地的git仓库上传到github **（可以直接看3.2实例1改进版）**
```
#初始化
git init demo
#把文件加入缓存区
git add git_learn.txt
#把缓存区文件加入本地仓库
git commit -m 'the first commit`
```
继续运用第二节的`demo`仓库，经过上述过程，我们已经有了本地的git仓库`demo`，接下来在github上创建一个同名仓库`demo`  
![image](https://user-images.githubusercontent.com/81409445/128623007-f3a75057-585e-41cc-aca6-818a46f4538c.png)  
点击右上角绿色按钮`code` 再如图点击复制远程仓库的地址。  
![image](https://user-images.githubusercontent.com/81409445/128623136-be8c1478-90dc-4bf1-9314-c50f860ac4b2.png)  
输入：
```
git remote add origin https://github.com/lu-kaijie/demo.git
```
关联远程仓库。其中`origin`为远程仓库默认名字。  
![image](https://user-images.githubusercontent.com/81409445/128623780-d080e1e4-b8ab-4fa5-9ee3-add1cfc7b29f.png)  
接下来使用`git pull`同步远程仓库，你的本地仓库`demo`中出现了远程仓库仅有的`README.md`则视为同步成功。
看别人教程说输入`git pull origin master`发现出错。  
![image](https://user-images.githubusercontent.com/81409445/128624052-42a8e44b-27da-4929-a3a1-bf69bef3e60d.png)  
于是尝试输入`git pull origin main`，发现也没成功，大概意思是不能混合两个不相关的仓库。  
尝试搜索解决方法，可以输入命令`git pull origin main --allow-unrelated-histories`，会弹出一个窗口叫你写一些说明为什么要混合，因为git通常不支持这样做。  
直接按`esc`再输入`:X`关闭就行。  
![image](https://user-images.githubusercontent.com/81409445/128624273-7f93fc48-c9ea-4858-813f-4d7374d977b0.png)  
一番周折后，我们可以看到`demo`仓库出现了`README.md`文件，说明同步成功。    
接下来在添加一个`git_learn_2.txt`文件。  
![image](https://user-images.githubusercontent.com/81409445/128624584-d23f9b03-f959-4407-91af-56d07a4ac79e.png)  
输入`git push origin master`把本地仓库`demo`主分支`master`内容提交到远程仓库`demo`，成功之后刷新`demo`仓库，显示`master`分支已经上传到远程仓库`demo`
## 3.2实例1改进版
实例一中间出了点小问题，不是正常流程。改正的地方是在github上创建一个同名仓库`demo2`的时候不要勾选 `add a README file`，应该是一个完全空白的仓库。  
![image](https://user-images.githubusercontent.com/81409445/128626282-52038914-2f17-4035-aa45-d1abb3620422.png)  
![image](https://user-images.githubusercontent.com/81409445/128626292-c283ce70-e22c-4576-9720-06aad968abb1.png)  
这次直接贴出完整流程来讲解  
![image](https://user-images.githubusercontent.com/81409445/128626553-b0fc6153-6c22-4d1a-b63f-7bec36701c96.png)  
![image](https://user-images.githubusercontent.com/81409445/128626570-8419b492-798b-4b35-9913-0b73ec02bd6a.png)  
`git remote -v`查看当前本地仓库关联的远程仓库地址。  
`git remote rm origin`取消与当前远程库的关联。  
`git remote add origin https://github.com/lu-kaijie/demo2.git`关联到新创建的远程仓库`demo2`.  
`git remote -v`再次查看当前本地仓库关联的远程仓库地址。此时已经变成了`demo2`
`git push -u origin main`把本地`demo`上传到远程`demo2`  
## 3.3实例2：在本地对github上的仓库改进
![image](https://user-images.githubusercontent.com/81409445/128627487-4285c9ea-0417-42df-9ce7-f279752f272f.png)  
![image](https://user-images.githubusercontent.com/81409445/128627512-50f66667-77e4-4fb3-9a43-570d8fce521c.png)  
![image](https://user-images.githubusercontent.com/81409445/128627523-054dd164-b8f7-44a6-9845-d23e8bbcff22.png)  
```
#在CoderLife目录下进入git Bash把远程仓库demo2克隆到本地，此目录下出现一个demo2子目录
git clone https://github.com/lu-kaijie/demo2.git
#转到克隆的demo2目录下
cd demo2
#随便找一个文件移到demo2内，查看、添加、上传
git status
git add java_repos.html
git commit -m 'commit to github'
#然后上传到github的demo2仓库，出错就多试几次
git push origin main
```
刷新github的demo2仓库，发现java_repos.html已经加入到demo2的主分支中。  
但并不支持直接对主分支修改。也可以先新建一个分支再修改。如图。
![image](https://user-images.githubusercontent.com/81409445/128627972-3891bbdc-3352-4111-9f45-fac91e1c41fa.png)  
![image](https://user-images.githubusercontent.com/81409445/128627993-426295c1-fb9d-451b-8004-4f702f7a8521.png)
此时刷新github的demo2 可以看到`my-branch`分支已经添加到远程仓库中。  
![image](https://user-images.githubusercontent.com/81409445/128628008-b74b129c-60cc-4934-bd7c-8c8243c6197e.png)




