目录转变为git管理仓库
Git init
添加文件进入git仓库
Git add
注释修改内容
Git commit -m
查看所有版本
Git log
简略 git log --pretty=oneline
修改回以前版本
^这个有几个就是第几个， ~d
d是几就是前第几
Git reset --hard HEAD^
Git reset --hard HEAD~1
返回未来的版本
Git reset --hard 版本号
Git reflog 历史命令

git clone git@github.com:hclg/learngit.git 克隆
ssh -T git@github.com 判断连接
ssh-keygen -t rsa -C "2249121951@qq.com" 创建远程连接钥匙
钥匙位置 ~/.ssh/id_rsa.pub
$ git branch dev 创建分支
$ git checkout dev 切换分支
简写 git checkout -b dev
	git switch -c dev
Git branch 查看分支
git merge dev 合并分支
 切换 switch 分支
git branch -d dev 删除分支
 在本地创建dev分支并与远程dev分支对应
     git checkout -b dev origin/dev
 切换到master分支
     git checkout master
 本地的dev合并到master上（如果遇到冲突解决完后再次提交即可）
     git merge dev
 推送到远程的master上
     git push origin master           
