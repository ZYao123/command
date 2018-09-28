# git常见命令整理

---
## 在当前目录新建一个Git代码库  
`git init`

---
## 添加指定文件到暂存区
`git add [file1] [file2]`
## 添加指定目录到暂存区，包括子目录
`git add [dir]`

---
## 提交暂存区到仓库区
`git commit -m [message]`

## 关联远程仓库
`git remote add origin https://github.com/ZYao123/command.git`

---
## 把本地库的所有内容推送到远程库上
`git push -u origin master`