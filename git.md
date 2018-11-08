# git常见命令整理

---
## 在当前目录新建一个Git代码库  
`git init`

---
## 添加指定文件到暂存区
`git add [file1] [file2]`  
添加指定目录到暂存区，包括子目录  
`git add [dir]`

---
## 提交暂存区到仓库区
`git commit -m [message]`

## 关联远程仓库
`git remote add origin https://github.com/ZYao123/command.git`

---
## 把本地库的所有内容推送到远程库上
`git push -u origin master`

## 强制推送到远程库上
`git push -f origin master`

---
## 查看版本之间的不同  
查看当前没有add 的内容修改  
`git  diff`  
查看已经add 没有commit 的改动  
`git diff --cached`  
查看当前没有add和commit的改动  
`git diff HEAD` 
`git status` 

---
## 查看加入git中的文件列表  
`git ls-files`  

---
## 将文件（夹）移出git
`git rm`  
删除暂存区或分支和本地工作区文件  
`git rm --cached`    
删除暂存区或分支中的文件
`git rm -r -n --cached "bin/"`  
展示要删除的文件表预览