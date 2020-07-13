# OneIndex

个人整合了“0oVicero0”和“Zisbusy”两位大佬的2020全新版本，内附Microsoft2020最新应用API使用方法。此项目针对于国际版（反正不是世纪互联那个版本，至于怎么改世纪互联版本看简介吧），下载后需要自己改动几处地方，还差一个网站图标没有加上，后期解决了会追加。

## 参考项目预览地址：

[0oVicero0大佬项目](https://github.com/0oVicero0/oneindex)
[Zisbusy大佬项目地址](https://github.com/Zisbusy/OneIndex-theme)
[我的项目](https://download.99couple.top/)

## 功能：

- 不用服务器空间，不走服务器流量
- 直接列onedrive目录，文件直链下载
- 可做图床，可预览文件，功能强大

## 一键安装（Debian 8）：

```
wget --no-check-certificate -qO- https://github.com/0oVicero0/oneindex/raw/master/install.sh |bash
```

## 添加 Redis 支持（Debian 8）：

```
# 安装 redis 支持
apt-get install -y redis-server php5-redis
# 重启 fcgiwrap-php 进程
bash /etc/init.d/fcgiwrap-php restart
# 后台选择 redis 模式, 并更新缓存.
```

## 创意整合：

1. 极大简化安装步骤。  
2. 一些样式美化修改。
3. 分页模式，加快页面预览速度。创意来自[oneindex-h](https://github.com/hang666/oneindex-h)   
4. 可后台自定义网站主标题,副标题。         
5. 可后台自定义每页显示项目数量。  
6. 对于flac格式音乐加入图标显示
7. 对于页面顶部添加动态效果美化
8. 添加了针对Apache服务器的伪静态配合文件（.htaccess），后台开启伪静态即可去掉/?/
9. 在图片下方添加下载地址、图片引用地址

## 安装：

1. 由于整合了美化，需要做一些改动，再进行安装

   - 打开 `view/nexmoe目录` 下 `的layout.php`文件 

   - 修改 第7行 、第9行 第19行 download.99couple.top 为自己下载站的域名（或者自己引用的目录）

   - 修改 第15行 链接里的`81895257`为自己QQ（或者自己引用的图片）

     修改18行的`99couple.top`为自己的博客域名，没有就还填下载站域名呗，小问题

   - 打开 `theme目录` 下 `style.css` 文件

   - 修改 第97行、第103行 download.99couple.top 为自己域名（或者自己引用的目录）

   - 至此美化改动完成

2. 针对于拥有个人下载站域名的同学来说，我们不应该中转到别人的域名下，加以如下修改

   - 打开`controller/AdminController.php`文件
   - 修改163行引号内的地址为你的下载站地址，必须是HTTPS协议的，微软强制。

3. 针对于国内比较富裕的同学可以直接重金包月续订世纪互联版本（不是世纪互联版本的自动跳过这一条）

   - 首先声明世纪互联版本确实快，因为数据中心就在国内，峰值达到4MB/s没问题。而国际版的小伙伴，就不要强求了，你的峰值再高也不可能高过世纪互联版本的用户的。
   - 打开根目录下的index.php文件
   - 将6、7行的注释去掉
   - 这样我们在获取应用ID和应用密钥的时候是跳转到世纪互联代理的网站来登录的
   - 别问我知道的，因为你国际版的账户ID根本不在世纪互联的库里面，如果国际版的小伙伴也将注释去掉，你在获取应用ID时登录你的账户时，会提示你没有这个用户。
   - 对了，大佬在魔改原版OneIndex时去掉了获取应用ID和密钥的跳转按钮，附上新版链接（微软已经于2020年强制应用注册接入Microsoft Azure了，有兴趣的小伙伴可以搜索相关知识）
   - [新版Microsoft Azure链接](https://portal.azure.com/#home)

4. 我们先来打开新版Microsoft Azure链接来注册应用

   - 打开Azure Active Directory
   - ![image-20200712114327996](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE0MzM1LnBuZw?x-oss-process=image/format,png)
   - 注册新的应用
   - ![image-20200712114504362](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE0NTA0LnBuZw?x-oss-process=image/format,png)
   - ![img-MheLLYkf-1594526637683](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE0NjQ1LnBuZw?x-oss-process=image/format,png)
   - ![image-20200712114904574](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE0OTA0LnBuZw?x-oss-process=image/format,png)
   - ![image-20200712115137320](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE1MTM3LnBuZw?x-oss-process=image/format,png)
   - ![image-20200712115304012](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE1MzA0LnBuZw?x-oss-process=image/format,png)
   - ![image-20200712115445024](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE1NDQ1LnBuZw?x-oss-process=image/format,png)
   - 到这里应用ID和密钥就注册完了

5. 安装OneIndex程序

   - 这个程序安装就不写了，网上多的很，就是把项目文件全部丢进你网站目录下面
   - 现在主要麻烦的就是这个应用ID和密钥强制接入Microsoft Azure了
   - 还有啥不懂的可以私信我哈。

6. 安装完会是这样，也可以点上面的预览链接去看看

![img-skQKbNNE-1594526637699](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWcuOTljb3VwbGUudG9wLzIwMjAwNzEyMTE1OTI2LnBuZw?x-oss-process=image/format,png)]

​     

## 重新安装：

删除 oneindex/config 下的所有文件即可.                
一键安装的地址: /var/www/oneindex/config               

## change log:  

18-03-29: 更新直链获取机制、缓存机制，避免频繁访问的token失效  
18-03-29: 解决非英文编码问题  
18-03-29: 添加onedrive共享的起始目录 功能  
18-03-29: 添加rewrite的配置文件  
18-03-29: 增加sqlite模式cache支持  
18-03-29: 添加缩略图功能  
18-03-29: 添加404判断  
18-03-31: 添加console  
18-04-13: 修复特殊文件名无法下载问题  
18-04-13: 添加命令行上传功能  
18-04-16: 更新 2.0 beta  
18-04-16: 更新展示界面  
18-04-16: 响应式，支持小屏设备  
18-04-16: 图片在线预览  
18-04-16: 视频在线播放  
18-04-16: 代码在线查看（js、css、html、sh、php、java、md等）  
18-04-16: README.md 支持，解析各目录下(onedirive目录下) README.md 文件，在页面尾部展示。  
18-04-18: 音频在线播放  
18-04-18: HEAD.md 支持，在页面头部展示   
18-04-18: .password 文件夹加密  
18-05-06: 在线视频播放器替换成 Dplayer  
18-05-06: 在线视频播放支持'mp4','webm','avi','mpg', 'mpeg', 'rm', 'rmvb', 'mov', 'wmv', 'mkv', 'asf'  
18-06-01: 支持个人账号  
18-06-01: cli文件夹上传（单线程）  
18-06-01: 管理后台(后台地址:?/admin 默认密码:oneindex)  
18-06-01: 不同后缀展示设置  
18-06-01: 文件直接输出  
18-06-01: 文件上传管理（后台） 
18-06-01: 增加index.html特性   
18-06-01: 图床功能   

## 需求：

1、PHP空间，PHP 5.6+ 打开curl支持  
2、onedrive 账号 (个人、企业版或教育版/工作或学校帐户)  
3、oneindex 程序   

## 计划任务：

[可选]**推荐配置**，非必需。后台定时刷新缓存，可增加前台访问的速度  

```
# 每小时刷新一次token
0 * * * * /具体路径/php /程序具体路径/one.php token:refresh

# 每十分钟后台刷新一遍缓存
*/10 * * * * /具体路径/php /程序具体路径/one.php cache:refresh
```

## 特殊文件实现功能：

` README.md `、`HEAD.md` 、 `.password`特殊文件使用  

可以参考[https://github.com/0oVicero0/oneindex/tree/files](https://github.com/0oVicero0/oneindex/tree/files)  

**在文件夹底部添加说明:**  

>在onedrive的文件夹中添加` README.md `文件，使用markdown语法。  

**在文件夹头部添加说明:**  

>在onedrive的文件夹中添加`HEAD.md` 文件，使用markdown语法。  

**加密文件夹:**  

>在onedrive的文件夹中添加`.password`文件，填入密码，密码不能为空。  

**直接输出网页:**  

>在onedrive的文件夹中添加`index.html` 文件，程序会直接输出网页而不列目录。  
>配合 文件展示设置-直接输出 效果更佳  

## 命令行功能：

仅能在php cli模式下运行  
**清除缓存:**  

```
php one.php cache:clear
```

**刷新缓存:**  

```
php one.php cache:refresh
```

**刷新令牌:**  

```
php one.php token:refresh
```

**上传文件:**  

```
php one.php upload:file 本地文件 [onedrive文件]
```