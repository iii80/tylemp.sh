### What is this repository for? 这个脚本作用 ###

* This is for those who need to quick set up LEMP on their Debian.  这脚本方便各位在Debian上快速搭建LEMP环境。 
* Besides, this can quickly set up Wordpress and other CMS without manually configure Mysql and Nginx. 此外，还可以在不需要手动设置Nginx和Mysql的情况下快速安装Wordpress和其它CMS。
* It also do some optimization and security work like deleting unneccesary components and changeing SSH port(manually). 此外，脚本还会进行优化和安全设置比如删除一些非必须系统组件和更改ssh端口(手动运行). 

### How do I get set up? 如何运行 ###

* wget http://w3.gubo.org/pubfiles/tylemp/9/tylemp.sh # Get script(pay attention and find right script for your version) 下载脚本(注意下载系统对应版本的脚本) 
* bash tylemp.sh stable # Optimize system and set up LEMP 优化系统并搭建LEMP环境  
* More in the Command List and Notes 更多的在“命令行列表”及“注意”里


### Command List 命令行列表###
```
bash tylemp.sh system # 优化系统，删除不需要组件，dropbear替代sshd
bash tylemp.sh exim4 # 更轻量级邮件系统
bash tylemp.sh mysql # 安装mysql
bash tylemp.sh nginx # 安装nginx，默认一个进程，可调整
bash tylemp.sh php # 安装php，包含php5-gd，可使用验证码
bash tylemp.sh stable # 安装上面所有，软件是debian官方stable源，版本较旧
bash tylemp.sh wordpress www.yourdomain.com # 一键安装wordpress, 数据库自动配置好。
bash tylemp.sh vhost www.yourdomain.com # 一键安装静态虚拟主机。
bash tylemp.sh dhost www.yourdomain.com # 一键安装动态虚拟主机，方便直接上传网站程序。
bash tylemp.sh typecho www.yourdomain.com # 安装typecho，提供数据库名，密码等自主添加完成安装
bash tylemp.sh phpmyadmin www.yourdomain.com # 一键安装phpmyadmin 数据库管理软件，用http://www.yourdomain.com/phpMyAdmin访问
bash tylemp.sh addnginx 2 #调整nginx进程，这里2表示调整后的进程数，请根据vps配置（cpu核心数）更改
bash tylemp.sh sshport 22022 #更改ssh端口号22022，建议更改10000以上端口。重启后生效。
bash tylemp.sh rainloop www.yourdomain.com  # 增加Gmail的web客户端一键安装
bash tylemp.sh carbon www.yourdomain.com  # 增加Carbon Forum的一键安装
```
 
### Notes 注意###
You can find configure files and log path in this part 在这部分你会看到主要的配置文件和日志文件路径

#### Path of conf 配置文件路径 ####
```
/etc/nginx/nginx.conf  #nginx Conf file / Nginx配置文件
/etc/php5/fpm/php.ini    # PHP conf file / php配置文件
~/.my.cnf                 # Mysql/MariaDB root user name and password / Mysql/MariaDB根用户名和密码
/etc/nginx/conf.d/          # Nginx conf for added websites / 已添加网站的Nginx配置文件
```

#### Path of log 日志文件路径 ####

```
/var/log/nginx   # Nginx log files path / Nginx 日志文件路径
/var/log/php5-fpm.log  # PHP log files path / PHP文件路径
/tmp/tylemp.log # Script running log / 脚本运行日志 
```


### Contribution guidelines 贡献准则###

* Everyone is welcome to contribute 欢迎所有人贡献代码
* Please spread the words to who need 请把这个脚本告知有需要的人

### How to debug / 出错该怎么办###
* Please firstly check the log ```/tmp/tylemp.log``` and try to solve the problem. If you can not handle it, please send this file to guboorg@gmail.com
* 请先检查```/tmp/tylemp.log``` 这个日志文件，如果实在不能解决请把这个文件发送到我的邮箱 guboorg@gmail.com


### Who do I talk to? 我应该和谁讨论###

* Repo owner or admin 所有作者和拥有者
* Other community or team contact 使用者