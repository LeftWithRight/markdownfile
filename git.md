# Git使用
## 创建Git仓库：
在本地创建一个Git仓库，可以通过以下命令来完成：  
```git init```
这将在当前目录下创建一个空的Git仓库
## 添加文件：
将需要管理的文件添加到Git仓库中：  
```git add <filename>```

```git add .      //添加全部文件```

## 提交更改：  
将添加到Git仓库的文件提交到版本控制系统中，可以使用以下命令：  
```git commit -m "commit message"```         //这将创建一个新的提交，并为其添加一条提交信息。

## 查看提交历史：
可以使用以下命令查看Git仓库中的提交历史：
```git log```

## 分支管理：

可以使用以下命令创建、切换和合并分支：  
``` 
git branch <branchname>        # 创建新分支
git checkout <branchname>      # 切换到指定分支
git merge <branchname>         # 合并指定分支到当前分支
git branch             #列出所有分支
git branch -r           #列出所有分支
git branch -d            #删除分支
git branch -dr <远程仓库分支>      #删除远程仓库分支
```

## 远程仓库管理：
可以使用以下命令与远程仓库进行交互：
```
git clone <url>                # 从远程仓库克隆
git pull                       # 从远程仓库拉取最新代码到本地
git push                       # 将本地代码推送到远程仓库  
```
## 远程仓库管理：  
可以使用以下命令与远程仓库进行交互：  
```  
git clone <url>                # 从远程仓库克隆代码到本地
git pull                       # 从远程仓库拉取最新代码到本地
git push                       # 将本地代码推送到远程仓库  
```

## 配置

1.  查看安装配置

   ```git config -l```

2. 配置 Git：进入到克隆的仓库目录中，并使用以下命令配置你的 Git 用户名和邮箱：
   ```
   git config --global user.name "Your Name"
   git config --global user.email "youremail@example.com"
   ```
3. 连接远程仓库：进入到仓库目录中，在终端或命令行界面中使用以下命令将本地仓库与远程仓库关联起来：
   ```
   git remote add origin <仓库URL>
   ```
   