# 问题回答

## 1
git init:在本地创建空的git仓库，位于当前文件夹
git add .将文件夹全部的两个文件（readme和程序）交入暂存区
git commit -m "test" 将当前暂存区的所有文件提交到仓库当前所在分支，留下提交记录

## 2
空仓库正常建立，本地仓库push成功，git remote -v输出：origin  git@github.com:Twin-Ghosts/fortest-2026-8-12-8-12.git (fetch)
origin  git@github.com:Twin-Ghosts/fortest-2026-8-12-8-12.git (push)

## 3.
main/master分支一般意味着整个项目具有正常功能的稳定版本，直接在上面修改容易破坏稳定性与影响正常使用；同时多个协作者各用一个分支也能避免交叉修改，无法分清责任与工作内容的情况。

## 4.

正常运行，git pull后代码中出现包括<<<<====>>>>的选择块  
终端信息:  
remote: Enumerating objects: 5, done.  
remote: Counting objects: 100% (5/5), done.  
remote: Compressing objects: 100% (3/3), done.  
remote: Total 3 (delta 0), reused 0 (delta 0 ), pack-reused 0 (from 0)  
Unpacking objects: 100% (3/3), 980 bytes | 122.00 KiB/s, done.  
From github.com:Twin-Ghosts/fortest-2026-8-12-8-12  
 * branch            for_test_4 -> FETCH_HEAD  
   e936b31..1428628  for_test_4 -> origin/for_test_4  
Auto-merging printer.py  
CONFLICT (content): Merge conflict in printer.py  
Automatic merge failed; fix conflicts and then commit the result.  
PS D:\fortest-git-20260812-1636>   
此时可以修改原文保留所需内容，即可正常推送。



## 5.
reset是回退到之前的某次提交，之后的记录删除：
（git log显示情况）

    test_5_wrong

    test_5_s2


    test_5_s1
---->
	 test_5_s2

    test_5_s1

revert是一次新的提交消除掉之前提交的影响：
（git log 显示情况）


    Revert "w"

    w


    2

此外，revert前需要commit 或 stash，而reset不需要。