test

second test

- [Git-](#git-)
- [零.安装及添加账户](#零安装及添加账户)
- [一.基本指令](#一基本指令)
- [二.应用场景](#二应用场景)
  - [1. 标准上传文件](#1-标准上传文件)
  - [2. 在你上传新版本前，有同事上传了新版本（代码更改位置不冲突）](#2-在你上传新版本前有同事上传了新版本代码更改位置不冲突)
  - [3. 在你上传新版本前，有同事上传了新版本(代码更改位置冲突)](#3-在你上传新版本前有同事上传了新版本代码更改位置冲突)
  - [4. 删除指定节点后续的所有节点](#4-删除指定节点后续的所有节点)
- [三.疑难杂症](#三疑难杂症)
# Git-
git使用说明；应用场景使用指南；git使用轮子大全
# 零.安装及添加账户
1. 检查git是否已经安装，输入git version命令即可，如果没有显示版本号表示没有安装git

2. 安装git
sudo apt-get install git

3. 配置git全局环境
git config --global user.name "用户名"
git config --global user.email "邮箱地址"

4. 生成ssh密钥
ssh-keygen -C 'you email address@gmail.com' -t rsa
会在用户目录~/.ssh/下建立相应的密钥文件。

5. 创建完公钥后，需要上传。
使用命令cd ~/.ssh进入~/.ssh文件夹，输入
Gedit id_rsa.pub
打开id_rsa.pub文件，复制其中所有内容。接着访问git网页，点击SSH公钥，标题栏可以随意输入，公钥栏把刚才复制的内容粘贴进去。

# 一.基本指令
1. git clone url地址
    
    第一次拉取项目时使用

2. git diff
    
    比较工作区和上一版本有何差异

3. git status 

    查看当前路径下的状态

4. git add .

    将工作区的所有变动放置于暂存区

5. git commit -m "提交时说明信息"

    进一步提交，并提交说明log

6. git push
    
    将更新内容推送至远程服务器

7. git pull

    将代码从远程服务器拉取到本地

8. git checkout -b （新分支名称（不需要双引号，同时去掉括号））

    创建新分支并切换至新分支

    等同于以下两个操作按顺序运行：

    创建新分支：git branch branchName

    切换到新分支：git checkout branchName

9.  git branch -d （新分支名称（不需要双引号，同时去掉括号））

    删除指定分支

10. git pull

    更新你的本地仓库至最新改动

11. git checkout .

    丢弃你所有的本地改动与提交

12. git checkout -- (文件名称)

    只丢弃选定文件的改动

13.  git reset --hard HASH

        返回到指定节点，不保留修改

14. git  reset HEAD (文件名称)

    取消已被add添加到暂存区的文件


# 二.应用场景

## 1. 标准上传文件
   1. git  status 
   
        查看当前路径下的状态

   1. git add .
        
        将工作区的所有变动放置于暂存区

   1. git commit -m "提交时说明信息"
        
        进一步提交，并提交说明log

   1. git push
        
        将更新内容推送至远程服务器

## 2. 在你上传新版本前，有同事上传了新版本（代码更改位置不冲突）
   1. git  status 
   
        查看当前路径下的状态

   1. git add .
        
        将工作区的所有变动放置于暂存区

   2. git commit -m "提交时说明信息"
        
        进一步提交，并提交说明log
   
   3. git  stash （若功能未开发完全，123步骤可省略）
   
        将未上传的文件暂存

   4. git pull
        
        将同事上传的最新代码拉取至本地
        
   5. git stash pop
        
        将修改取出

## 3. 在你上传新版本前，有同事上传了新版本(代码更改位置冲突)

 1. 初始代码
 
    ![初始代码]( https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_%E5%88%9D%E5%A7%8B%E4%BB%A3%E7%A0%81.jpg?raw=true "初始代码")

 
 2. 在另一个目录下clone 工程，并更新代码，而后上传
    ![另一文件夹下更新的代码]( https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_%E5%8F%A6%E4%B8%80%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%8B%E6%9B%B4%E6%96%B0%E4%BB%A3%E7%A0%81.jpg?raw=true "另一文件夹下更新的代码")
 
 3. 在原目录下相同位置更新代码并上传，产生冲突
     ![相同位置更新代码并上传，产生冲突]( https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_push%E4%BA%A7%E7%94%9F%E5%86%B2%E7%AA%81.jpg?raw=true "相同位置更新代码并上传，产生冲突")
 
 
 4. pull拉取远程最新代码
      ![pull拉取远程最新代码（代码段）]( https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_%E5%86%B2%E7%AA%81%E4%BA%A7%E7%94%9F%E5%90%8E%E7%9A%84pull.jpg?raw=true "pull拉取远程最新代码（代码段）")
    ![pull拉取远程最新代码（shell端）]( https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_%E5%86%B2%E7%AA%81%E4%BA%A7%E7%94%9F%E5%90%8E%E7%9A%84pull%E7%9A%84shell%E5%91%BD%E4%BB%A4%E8%A1%8C.jpg?raw=true "pull拉取远程最新代码（shell端）")
 
 5. 手动修改冲突
   
     ![手动修改冲突](  https://github.com/lienguang0624/Git-/blob/main/img/%E5%86%B2%E7%AA%81%E8%AF%95%E9%AA%8C_%E4%BF%AE%E6%94%B9pull%E5%90%8Egit%E7%94%9F%E6%88%90%E7%9A%84%E5%86%B2%E7%AA%81%E5%AF%B9%E6%AF%94.jpg?raw=true "手动修改冲突")

 6. 而后执行以下命令即可
    1. git add -u （-u参数表示把文件区跟踪的文件添加到缓存区）
    2. git commit -m "message"
    3. git push

## 4. 删除指定节点后续的所有节点
1. 先使用gitk找到分割节点的SHA1 ID,copy下来
2. 在shell中git reset --hard *********************，进行回退
3. 使用git push -f进行推送

# 三.疑难杂症
**1. git使用commit命令后显示Author identity unknown的解决方法：**

   在git命令行中重新输入命令：

   先输入：$ git config --global user.name "你的名字"

   回车后，

   再输入：$ git config --global user.email "你的邮箱地址"

   完成后再提交就没问题了。

   ![Author identity unknown](https://github.com/lienguang0624/Git-/blob/main/img/Author%20identity%20unknown.png?raw=true "Author identity unknown")

**2. ssh连接服务器出现Agent admitted failure to sign using the key错误**

在当前用户下执行命令：ssh-add即可解决
  ![Agent admitted failure to sign using the key](https://github.com/lienguang0624/Git-/blob/main/img/Agent%20admitted%20failure%20to%20sign%20using%20the%20key.png?raw=true "Agent admitted failure to sign using the key")


**3. git分支切换时，提示Deletion of directory '*********' failed. Should I try again？**


问题的原因是你工作目录有某些文件正在被程序使用，这个程序多半是Idea,vsCode或者eclipse,当然也可能是其他程序。


解决方案不是简单的选择y或者n，而是关闭vsCode，让vsCode把这些文件释放掉。


