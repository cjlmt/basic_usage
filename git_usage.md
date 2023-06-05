- ### git === 分布式版本控制系统
- ### 作用：
  * **每次修改很多文件使用git提交后，git会创建一个项目版本记录所有文件**
  * 其他人可以同时修改，并且自动合并修改的部分，按行来对比文件不同（doc是二进制文件不行，docx可以）
- ### 前提条件：安装git和vscode环境
- ### 前置知识(终端)：
  * pwd：显示当前会话所在目录
  * ls：显示当前目录下所有的文件
  * cd ..：跳转到上一级目录
  * cd .\xxx\：跳转到对应目录
  * clear：清空当前对话
- ### 使用：
  * 查看版本号 git version
  * 修改用户昵称 git config --global user.name "cjlmt" （查看使用git config user.name）
  * 修改用户邮箱 git config --global user.email "604495355@qq.com" 
  * git init：当前目录初始化，创建一个.git隐藏文件夹。这个文件夹的作用就是**保存项目文件每个git版本记录和变化**
  * git add xxx.xx：把文件加进git版本控制系统中
  * git add .：把当前目录的全部文件加进git中（**add后只是暂存更改**）
  * git commit：保存提交记录到.git文件夹，将暂时保存的变更提交固定成一个版本。进入vim终端编辑器，按下a/i进入编辑模式，写下提交说明，按下esc退出编辑模式，再输入英文冒号:wq(write,quit)表示保存并退出
    - **提交说明的简化操作：直接使用git commit -m "提交说明"**
    - git commit的提交说明有一些规范，正式项目需要讲究
  * git log：查看提交日志，每次提交会用一串随机id标识
- ### vscode进行git操作
  * 修改文件后，左侧源代码管理亮起，点击具体更改的文件，可以看到与改动前的对比
  * 点击顶部的√，可以执行git add和git commit，之后需要提供提交消息，回车结束commit
- ### 回退到某个版本
  * git reset --hard xxx(commitId)：就可以回退到对应的版本，log提交日志也会回退(--hard表示硬重置)
- ### 不希望reset清空，而是可以在不同版本中切换？
  * 使用分支branch，把当前版本复制一份。一个团队开发离不开分支
  * commit时给分支起一个分支名(0.2)，提交后用git brance xxx(分支名)创建一个分支，或者点击发布branch按钮
  * git branch -a：查看所有分支
  * git checkout xxx(分支名)：切换分支，如果切换为主分支则分支名写master
  * 在不同分支上写代码，可以使用git merge命令将各个分支合并
- ### GitHub提供公共git仓库服务，支撑团队协作
  * 新建一个项目(云端以及本地)，本地项目先init - 添加readme.md - add - commit（git并不要求本地仓库名和远程仓库名相同）
  * git branch -M main：创建一个main分支，并把主分支切换为main
  * git remote add origin https://github.com/cjlmt/example.git ：添加一个远程仓库地址，给项目设置一个网盘地址，知道上传到哪里
  * git push -u origin main：推送上传到github仓库，随后会提示输入GitHub的邮箱和密码（可能因为网络原因要多推送几次）
  * 设置好后，GitHub仓库就有了你commit到git中的文件
- ### 参与开发开源项目
  * fork要开发的开源项目
  * 点击code，复制仓库的https链接
  * 本地文件夹终端中输入：git clone https://github.com/cjlmt/example.git .  (注意尾部添加空格+英文句号)把服务器上的仓库克隆到本地
  * 此时本地仓库的推送是基于自己GitHub仓库的地址(git remote -v 查看)
  * 设置上游仓库链接(代码库)：git remote add upstream https://github.com/github_official/example.git
  * 要给别人加功能，先创建一个分支：git checkout -b xxx(创建并切换)
  * 创建members文件夹，创建cjlmt.json文件，里面写一个对象包含你的信息，随后add并commit，最后push(第一次push必须要后面的参数指明push源和分支)
    - git push -u origin xxx() 然后我们的仓库已经有xxx这个分支了
  * 此时去作者的仓库下点击pull requests拉取请求(pr)，点击新建pr，选择我们仓库的xxx分支与base根源仓库的main分支进行比较
    - 如果显示'able to merge'可以合并，则填写pr信息，创建pr
    - 作者操作合并进主项目
    - 如果显示不可合并，则你写代码的时候，作者已经进行了代码的更改，导致你俩的版本不一致
      * 解决办法：更新本地版本：git fetch upstream，从上游更新最新代码。执行：git merge upstream/main，把远程的最新代码合并到自己的分支中，再git push

其余很多的git功能实际工作中再查
