<<<<<<< HEAD
- [Git-](#git-)
- [零.安装及添加账户](#零安装及添加账户)
- [一.基本指令](#一基本指令)
- [二.应用场景](#二应用场景)
  - [标准上传文件](#标准上传文件)
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

12.  git reset --hard HASH

    返回到指定节点，不保留修改

13. 

# 二.应用场景

## 标准上传文件
   1. git  status 
   
        查看当前路径下的状态

   1. git add .
        
        将工作区的所有变动放置于暂存区

   1. git commit -m "提交时说明信息"
        
        进一步提交，并提交说明log

   1. git push
        
        将更新内容推送至远程服务器

应用场景2：


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

   
=======
# Git-
git使用说明；应用场景使用指南；git使用轮子大全
>>>>>>> parent of 8456752 (readme update)
