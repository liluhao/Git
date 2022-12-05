



# 1.status

```yaml
#查看指定文件状态命令：git status [filename]

#查看所有文件状态命令：git status
 
#精简的方式显示文件状态命令：git status -s
```

初始化仓库、新建1.txt、新建2.txt、Untracked status：

![image-20221117122920776](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117122920776.png)

![image-20221117123750622](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117123750622.png)

编辑1.txt、并进行add与commit：

![image-20221117123136242](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117123136242.png)

再次进行编辑1.txt、并进行add与commit、Modified  status：

![image-20221117123257444](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117123257444.png)

![image-20221117123340730](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117123340730.png)

# 2.log

```yaml
# git log --pretty=oneline 前面的唯一标识代码太长，实际上我们只需要前面几位就行了

# git log --pretty=oneline --abbrev-commit 唯一标识短，abbrev是优化的意思，优化commit

# git log --pretty=oneline --abbrev-commit --all 里面会显示分支、tag等，不直观

# git log --pretty=oneline --abbrev-commit --all --graph 很直观的可以知道有几个线在开发、几个线合并等信息

注：上面四行指令最后面都是系统默认加上 --decorate 的 ，比如：
git log --pretty=oneline --abbrev-commit --all --graph --decorate #跟上面效果是一样的
注：我们在一下图片中可能看不出区别，是因为项目太小了
```

初始化仓库、新建1.txt并提交：

![image-20221117125602794](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117125602794.png)

新建2.txt并提交：

![image-20221117125627939](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117125627939.png)

![image-20221117125827979](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117125827979.png)

# 3.文件夹

```yaml
#git里如果有一个空文件夹的话，git是不会识别到的
```

![image-20221117132050303](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117132050303.png)

![image-20221117132228038](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117132228038.png)

# 4.版本回退、版本更新

```yaml
#版本回退作用：版本切换

#命令形式：git reset --hard commitID
commitID 可以使用 git-log 或 git log 指令查看

#如何查看已经删除的记录
git reflog，这个指令可以看到已经删除的提交记录
```

新建1.txt并提交、新建2.txt并提交：

![image-20221116202120116](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116202120116.png)

![image-20221116202229373](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116202229373.png)

版本2回退到版本1：

![image-20221116202908441](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116202908441.png)

版本1更新到版本2：

![image-20221116203044916](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116203044916.png)

# 5.分支

```yaml
#查看本地分支命令：git branch

#创建本地分支命令：git branch 分支名 

#切换到存在的分支命令：git checkout 分支名 

#创建并切换到不存在的分支命令：git checkout -b 分支名 

#合并分支命令：git merge 分支名称 

#删除分支命令
不能删除当前分支，只能删除其他分支
git branch -d b1 删除分支时，需要做各种检查
git branch -D b1 不做任何检查，强制删除

#解决冲突
当两个分支上对文件的修改可能会存在冲突，例如同时修改了同一个文件的同一行，这时就需要手动解决冲突，解决冲突步骤如下：
1. 处理文件中冲突的地方
2. 将解决完冲突的文件加入暂存区(add)
3. 提交到仓库(commit)

#git log --pretty=oneline --all --graph --abbrev-commit
```

查看本地master分支、并新建1.txt提交：

![image-20221116205510001](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116205510001.png)

创建并切换到luhao-dev分支：

![image-20221116205719853](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116205719853.png)

切换到master分支：

![image-20221116210008334](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116210008334.png)

切换到luhao-dev分支：

![image-20221116210052692](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116210052692.png)

在luhao-dev分支新建并2.txt提交：

![image-20221116210245383](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116210245383.png)

切换到master分支：

![image-20221116210333519](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116210333519.png)

合并分支：

![image-20221116212413858](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116212413858.png)

![image-20221116212630510](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116212630510.png)

切换到luhao-dev分支：

![image-20221116212619179](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116212619179.png)

切换到master分支：

![image-20221116212717549](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116212717549.png)

删除分支：

![image-20221116212836602](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116212836602.png)

![image-20221116214222516](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116214222516.png)

# 6.推送远程仓库

**复用“5.分支”**

```yaml
#添加远程版本库命令：git remote add [shortname] [url]
git remote add origin  https://gitee.com/llh_425/gitstudydemo1.git
一个本地仓既可以对应一个远程仓库也可以对应多个远程仓库，不过一般情况下都是一个本地仓库对应一个远程仓库，需要为远程仓库起一个名字，可以随便起，但一般大家都起名origin，是统一的；回车后没有提示错误就表示成功了，remote是远程的意思，adj

#显示所有远程仓库命令：git remote、git remote -v

#显示某个远程仓库的信息：git remote show url

#删除远程仓库命令：git remote rm shortname

#git push [-f] [--set-upstream] [远端名称 [本地分支名][:远端分支名] ]
如果远程分支名和本地分支名称相同，则可以只写本地分支 git push origin master;
-f 表示强制覆盖（如果本，地代码与云端代码修改了同一个东西，这个时候会有冲突，云端不让我们push，-f的意思就是不管云端如
何本地都要强制推送并覆盖云端;大部分公司都把这个命令禁了，防止小白把公司文档覆盖）;
--set-upstream 推送到远端的同时并且建立起和远端分支的关联关系；
```

推送：

![image-20221116214835436](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116214835436.png)

显示所有远程仓库、显示某个远程仓库的信息：

![image-20221117115205857](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117115205857.png)

![image-20221116215918444](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116215918444.png)

![image-20221116220052179](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116220052179.png)

删除远程仓库：git remote rm 

![image-20221116220645227](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116220645227.png)

# 7.分支冲突

35前不用再看

64页往后不用再看

新建file01.txt提交；

修改file01.txt为update count=1提交

![image-20221205162034496](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205162034496.png)

新建dev01分支；

在master分支下新建.gitignore,可以看到提交.gitignore是被提交到了master分支上去了，并没有被提交到dev01分支上去了，对dev01没有任何的影响，即master分支比dev01分支多进行了一次提交

![image-20221205162326695](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205162326695.png)

切换分支到dev01上,切换完之后发现.gitignore消失了, git-log可以看到head指向谁,谁就是当前分支;

git checkout master 切换分支到master上,切换完之后发现.gitignore 又出现了,文件结构发生了变化 

![image-20221205162710438](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205162710438.png)

![image-20221205162748209](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205162748209.png)

创建并且切换到此新建的分支dev02;

切换到dev01分支,touch 在dev01分支上创建一个新文件file02.txt；

切换到master分支 

![image-20221205164401227](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205164401227.png)

![image-20221205164611415](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205164611415.png)

![image-20221205164709335](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205164709335.png)

dec01分支上面的全部都合并到master分支上面 ，输入完这个命令后会自动进入文本编辑页面，q! 直接退出;

删除dev01分支与dev02分支（删除某个分支的时候，必须先切换到别 的分支上去，即不能在当前分支上把当前分支删除了，当前已经在master分支上 了）；

创建一个新分支dev并切换

![image-20221205165836436](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205165836436.png)

![image-20221205165045680](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205165045680.png)

![image-20221205165903177](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205165903177.png)

![image-20221205165801432](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205165801432.png)

![image-20221205165747014](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205165747014.png)

![image-20221205170206321](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205170206321.png)

dev与matser修改file01.txt

![image-20221205171024413](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171024413.png)

![image-20221205171131345](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171131345.png)

![image-20221205171353700](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171353700.png)

![image-20221205171312669](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171312669.png)

![image-20221205171335450](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171335450.png)

把dev分支合并到当前分支master上去；

进行解决冲突

![image-20221205171919962](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171919962.png)

![image-20221205171950401](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205171950401.png)

删掉dev分支，分支太多影响查看；

创建一个新分支dev02并切换，新建file03.txt；

切换到master分支后再删除dev02分支，此时发现 dev02分支删除不了了，原因是dev02没有合并到master上面；

使用D可以强制删除

![image-20221205172518219](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205172518219.png)

![image-20221205172538540](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205172538540.png)

![image-20221205172612533](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205172612533.png)

![image-20221205172639931](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205172639931.png)

![image-20221205172658671](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205172658671.png)

# 8.快进模式

**复用“7.分支冲突”**

git merge dev 可以看到一个词，这就是快进模式（等效于dev合并到 master上，虽然git-log后系统没有合并的提示）

![image-20221205180326949](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205180326949.png)

![image-20221205180412658](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205180412658.png)

![image-20221205180433327](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205180433327.png)

发现直接把origin/master给拿到了上面去，这其实也是快进模式

![image-20221205210406556](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205210406556.png)

# 9.set-upstream

```yaml
# --set-upstream 推送到远端的同时并且建立起和远端分支的关联关系；
git push --set-upstream origin master:master 不仅要推送也要绑定关系
git push 第二次再需要把本地master推送到远端master分支的时候的代码,如果当前分支已经和远端分支关联，则可以省略分支名和远端名
```

![image-20221205205955220](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205205955220.png)

![image-20221205210011837](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205210011837.png)

![image-20221205210248437](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205210248437.png)

# 10.clone

```yaml
# git clone <repo> <directory>
git clone https://gitee.com/llh_425/gitstudydemo1.git #在后面可以指定下载到本地后的文件夹名字，如果不指定的话就默认就跟远程仓库的名字一模一样
git clone https://gitee.com/llh_425/gitstudydemo1.git hello-git #在后面可以指定下载到本地后的文件夹名字，如果不指定的话就默认就跟远程仓库的名字一模一样
```

# 11.fetch pull

```yaml
# git fetch [remote name] [branch name] 
抓取命令，抓取指令就是将仓库里的更新都抓取到本地，不会进行合并
remote name，类似叫origin；branch name是指我们想把远端的哪一个分支的更新拉到本地来
如果不指定远端名称和分支名，则抓取远程和本地关联的所有分支 

# git pull [remote name] [branch name] 
拉取命令，拉取指令就是将远 端仓库的修改拉到本地并自动进行合并，等同于fetch+merge 
如果不指定远端名称和分支名，则抓取所有并更新当前分支（比如如果我们当前在master分支上，我们就更新master分支）
```

rep:

![image-20221205224232846](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205224232846.png)

![image-20221205224246792](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205224246792.png)

![image-20221205224333732](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205224333732.png)

demo:

发现demo里没有dev分支

![image-20221205224906517](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205224906517.png)

![image-20221205224918182](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205224918182.png)

rep：

发现直接把origin/master给拿到了上面去，这其实也是快进模式

![image-20221205225914910](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205225914910.png)

demo：

git fetch 可注意到origin/master在master上面 ；

git-log 看文件结构知道当前分支还在原来的master上；

git merge origin/master （把远端的分支提交给合并到master上面来）（远 程分支也是分支）;

发现直接把origin/master给拿到了上面去，这其实也是快进模式

![image-20221205230505302](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205230505302.png)

rep：

发现直接把origin/master给拿到了上面去，这其实也是快进模式

![image-20221205231027628](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205231027628.png)

![image-20221205231039947](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205231039947.png)

demo：

发现直接就合并过来了

![image-20221205231321583](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205231321583.png)

rep:

![image-20221205231612591](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205231612591.png)

demo:

![image-20221205232255836](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205232255836.png)

![image-20221205231954927](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205231954927.png)

![image-20221205232309338](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205232309338.png)

![image-20221205232340733](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205232340733.png)

rep:

对比两个，一模一样

![image-20221205232745732](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221205232745732.png)

# 12.IDEA

```yaml
#红色：工作区文件（只针对文件，不指文件夹）
#蓝色：修改了本地仓库文件，即在本地仓库管理下的某个文件的内容被修改了的话，文件的颜色就会显示为蓝色
#绿色：暂存区文件，提交到暂存区的文件在idea上是绿色的（只针对文件，不指文件夹）
#正常颜色：本地仓库文件，即所有文件提交到本地仓库后，文件颜色都会处于正常的颜色
#黄色：被.gitignore标注的文件
```

0.显示.git，点文件，点设置，点编辑器，点文件类型，点忽略的文件与文件夹，点.git,点减号，点应用，点确定，然后文件结构显示如下（发现可以看到.git文件夹）

![image-20221117134305816](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117134305816.png)

1.这个提交会相对的弱化我们在gitbash里面的各个区，即勾选"未进行版本管理的文件"下面的文件然后点击“提交”后IDEA是默认把某个文不仅提交到暂存区也提交到本地仓库区（IDEA是默认一起进行提交）：

![image-20221117133642515](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117133642515.png)

2.右键某个文件或文件夹-----点"git"----点“+添加”，即将某个文件提交到暂存区

![image-20221117135046074](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117135046074.png)

![image-20221117134705358](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117134705358.png)

![image-20221117134625636](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117134625636.png)

![image-20221117135153521](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117135153521.png)

![image-20221117135140153](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221117135140153.png)

3.我们在进行勾选"未进行版本管理的文件"下面的文件然后点击“提交”时，尽量只勾选代码进行提交，不要勾选.idea文件夹以及.iml文件等，因为这些文件都是由IDEA开发工具自动创建的，别人的IDEA开发工具版本可能与自己的不一致，别人拉取下的代码可能会报错

4.假如在idea中，我们把一个很大的项目导入进了idea里，然后再对其进行初始化仓库，此时所有代码均是处于工作区的，文件全都处于在"未进行版本管理的文件"下面
5.假如在idea中，我们新建了一个文件夹，然后在里面写了几个文件，然后再对其进行初始化仓库，此时所有文件均是处于工作区的，文件全都处于在"未进行版本管理的文件"下面



