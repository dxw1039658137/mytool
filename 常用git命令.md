## 常用git命令

1. git clone git@192.168.1.124:Terminal/4G_Common.git

2. 有几个^就会打几个patch，从最近一次打起 

   git format-patch HEAD^
   
3.  git push origin --tags
	推送tag到远程仓库
	
4. 解决二进制冲突

   git checkout FILE --ours [ --theirs ]

   –ours 表示检出当前分支,即保存当前分支的改动,丢弃另外分支的改动.
   –theirs 表示检出另外分支, 即保存另外分支的改动,丢弃当前分支的改动.
   
5.  git更新远程仓库代码到本地

```
  //在本地新建一个temp分支，并将远程origin仓库的master分支代码下载到本地temp分支
   git fetch origin master:tmp 

   //来比较本地代码与刚刚从远程下载下来的代码的区别
   git diff tmp 

   //合并temp分支到本地的master分支
   git merge tmp

   //如果不想保留temp分支 可以用这步删除
   git branch -d temp
```

6. 创建远程分支

   git remote add origin 地址

   git push origin 本地分支：远程分支

   

7. 拉取远程分支，并创建分支

   方法一
   使用如下命令：

   git checkout -b 本地分支名x origin/远程分支名x

   使用该方式会在本地新建分支x，并自动切换到该本地分支x。

   采用此种方法建立的本地分支会和远程分支建立映射关系。

   方式二
   使用如下命令：

   git fetch origin 远程分支名x:本地分支名x

   使用该方式会在本地新建分支x，但是不会自动切换到该本地分支x，需要手动checkout。

   采用此种方法建立的本地分支不会和远程分支建立映射关系。

8. clone 指定分支

   git clone 指定分支：git clone -b 分支名称 项目地址
   
9. 删除远程分支

   git push origin --delete 【分支名】
   
10. 删除远程关联

    git remote **remove** origin

11. 新建远程关联

    git remote **add** origin https://xxxxxxx/wangdong/helloworld.git 

    git **push** -u origin master
    
12. git push --force 强制推送

