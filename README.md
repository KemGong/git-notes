# git使用技巧
**一些在实战中的git使用技巧跟记录**

1. 查看所有分支 

   `
   git branch -a
   `
1. 创建新分支并切换到分支

   `
   git checkout origin/分支路径名 -b 分支名
   `
1. 切换到远程分支，并取一个本地名字（-b后面接新分支的名字）推荐使用 统一一下 

   `
   git checkout -b newbranch origin/oldbranch
   `
1. 查看提交的log信息
   
   `
   git log
   `

1. 错误删除git代码或文件后恢复
   
   `
   git restore 
   `
1. 将远程获取最新的版本到本地
   
   `
   git pull origin feature/test_branch
   `
1. 提交代码到远端

   `
   git push origin my:feature/test_branch
   `
1. 打tag 

   `
   git tag v1.0.1 -m "FC test version" 9eceda13
   `
1. 将tag提交到远端
   
   `
   git push origin --tag
   `
1. 如果不能查看到所有分支没使用
   
   `
   git fetch
   `
1. 代码回滚
   * 在本地仓库回退

      `
      git reset --hard HEAD~1 //在本地仓库回退一次提交
      `

      `
      git reset --hard 1234566777
      `
   * 强制push到远端

      `
      git push -u origin feature/Cheerios_test（本地分支）:my_modify（远端分支） -f（强制）
      `

      `eg: git push origin my_battery:gongzheng/battery_voltage --force`
1. 修改远程分支名称

   [修改远程分支](https://juejin.im/post/6844903880115896327)

1. 基于某个分支创建分支,推送到git  
   创建分支  
   `
   git checkout -b youcreatbranch origin/oldbranch
   `  
   推送到git  
   `
   git push origin youtcreatbranch
   `  
1. 撤销远端已经push到远端的commit  
    `
    git reset --hard <版本号>
    `  
    `
    git push origin <分支名> --force
    `  
    `eg: git reset --hard 12345678`  
    `
    git push origin my:feature/Cheerios_test --force
    `  
1. 删除远程分支  
   `
    git push origin --delete <remote_branchname>
   `  
1. 删除本地分支  
   `
   git branch -d <BranchName>
   `  
1. git rebase  
   `
   git rebase <origin branch>
   `  
   *不要进行git pull，不然会出现一份重复的commit提交信息*  
   git push就ok  
   `
   git rebase origin/cheerios_dev
   `  
   `
   git push origin my_rebse:feature/board_test
   `  
1. 切换不同的版本  
   `
   git checout -b yourbranch historyversion
   `  
   `
   eg: checout -b my_roolback 123456789
   `  
1. 查看历史文件修改  
   `
   git show commit-id lookfiel
   `  
   `
   eg: git show 12345678(hash)  hello.c
   `