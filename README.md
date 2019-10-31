# 我的配置

> 增加git远程数据库
    
    git remote add origin git@github.com:waihoyu/node-shop.git

> git 清空所有commit记录方法

    说明：例如将代码提交到git仓库，将一些敏感信息提交，所以需要删除提交记录以彻底清除提交信息，以得到一个干净的仓库且代码不变

    1.Checkout
    git checkout --orphan latest_branch

    2. Add all the files
    git add -A

    3. Commit the changes
    git commit -am "commit message"

    4. Delete the branch
    git branch -D master

    5.Rename the current branch to master
    git branch -m master

    6.Finally, force update your repository
    git push -f origin master


> 解决macOS catalina 安装mongodb无法启动 出现Read-only file system问题

    最近把macOS升级到catalina后，安装mongoDB时，没有办法在目录下创建/data/db，提示Read-only file system（仅只读文件系统）。
    解决办法： 在终端执行下面两条命令：

    sudo mount -uw /
    killall Finder
    1
    2
    然后就可以执行啦

    mkdir -p /data/db
    1
    在启动mongodb前，还要对该文件夹赋予权限：

    sudo chown -R xxx /data/db   (XXX替换为当前登录的用户名)
    1
    这个只是临时开放系统文件权限的方法，Mac重启后如果还要对在根目录下创建文件，需要再次执行上面两条命令。

    https://www.reddit.com/r/MacOS/comments/caiue5/macos_catalina_readonly_file_system_with_sip/et94g0e/
    上面这个链接有个老外写了个启动时执行的脚本，感兴趣的可以去问他要。

