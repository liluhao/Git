# 1.版本回退、版本更新

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

# 2.分支

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

在luhao-dev分支新建并1.txt提交：

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

# 3.推送远程仓库

**复用“2.分支”**

```yaml
#添加远程版本库命令：git remote add [shortname] [url]
git remote add origin  https://gitee.com/llh_425/gitstudydemo1.git
一个本地仓既可以对应一个远程仓库也可以对应多个远程仓库，不过一般情况下都是一个本地仓库对应一个远程仓库，需要为远程仓库起一个名字，可以随便起，但一般大家都起名origin，是统一的；回车后没有提示错误就表示成功了，remote是远程的意思，adj

#显示所有远程仓库命令：git remote -v

#显示某个远程仓库的信息：git remote show url

#删除远程仓库命令：git remote rm shortname


# git push [-f] [--set-upstream] [远端名称 [本地分支名][:远端分支名] ]
如果远程分支名和本地分支名称相同，则可以只写本地分支 git push origin master;
-f 表示强制覆盖（如果本，地代码与云端代码修改了同一个东西，这个时候会有冲突，云端不让我们push，-f的意思就是不管云端如
何本地都要强制推送并覆盖云端;大部分公司都把这个命令禁了，防止小白把公司文档覆盖）;
--set-upstream 推送到远端的同时并且建立起和远端分支的关联关系；
```

推送：

![image-20221116214835436](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116214835436.png)

显示所有远程仓库、显示某个远程仓库的信息：

![image-20221116215918444](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116215918444.png)

![image-20221116220052179](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116220052179.png)

删除远程仓库：git remote rm 

![image-20221116220645227](https://mdmdmdmd.oss-cn-beijing.aliyuncs.com/img/image-20221116220645227.png)