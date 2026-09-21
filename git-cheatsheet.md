# Git 学习命令速查表

## 查看状态

```bash
git status --short --branch
查看当前分支、文件修改和本地与远程的同步状态。
保存修改
git add 文件名
git commit -m "说明"
git add 把指定文件放入暂存区，git commit 把暂存区保存为本地版本。
查看历史
git log --oneline --decorate --all
以简洁格式查看所有分支的提交历史和分支标记。
分支
git branch
git switch -c 分支名
git switch 分支名
git branch 查看分支，switch -c 创建并切换到新分支，switch 切换到已有分支。
合并与冲突
git merge 分支名
把指定分支合并到当前分支。冲突时需要手动删除冲突标记，再执行 git add 和 git commit。
远程同步
git push origin main
git pull origin main
push 是本地到远程，pull 是远程到本地。
查看和撤销修改
git diff
git diff --staged
git restore 文件名
git revert 提交号
diff 查看差异，restore 处理未提交修改，revert 用新的提交撤销旧提交。
其他工具
git stash
git cherry-pick 提交号
git rebase main
stash 临时保存未提交修改；cherry-pick 复制指定提交；rebase 以目标分支为基础重新安排当前分支提交。

这里的内容是对之前命令的总结，不需要新学命令。

---

# 第四阶段：检查修改

保存后执行：

```bash
git status --short
预期：
?? git-cheatsheet.md
然后查看内容差异：
git diff -- git-cheatsheet.md
这里的新格式需要解释：
git diff -- git-cheatsheet.md
- git diff：查看差异；
- --：告诉 Git，后面开始是文件路径；
- git-cheatsheet.md：只查看这个文件。
为什么要写 --？
当文件名可能和 Git 的选项或分支名混淆时，-- 可以明确告诉 Git：
我后面写的是文件，不是命令参数。

因为这是一个新文件，git diff 可能看不到未跟踪文件的内容，这很正常。Git 还没有开始跟踪它。