### Debian普通用户添加sudo权限

**安装sudo**

```bash
su #切换至root用户  

apt-get install sudo #安装sudo
```

**方法一**:比较简单

```bash
/usr/sbin/usermod -aG sudo username  #将username改成你的用户名
```

**方法二**：

1、添加sudoers文件编辑权限，安装vim

```bash
chmod +w /etc/sudoers apt-get 

install vim
```

2、编辑该文件 

```bash
vim /etc/sudoers
```

在root     ALL=(ALL:ALL) ALL下面添加如下行

```bash
toney    ALL=(ALL:ALL) ALL                        # 用户user执行sudo时需要密码。 

#toney   ALL=NOPASSWD:ALL                         # 用户user执行sudo时不需要密码。 

#toney   ALL=NOPASSWD:/etc/network/interfaces     # 用户user执行只有sudo执行/etc/network/interfaces的权限，执行时不需要密码。
```

3、恢复该文件的只读权限

```bash
chmod -w /etc/sudoers 
```

```bash
#还没有测试用过
# echo "username  ALL=(ALL) ALL" >> /etc/sudoers
或者
# echo "username  ALL=(ALL:ALL) ALL" >> /etc/sudoers
```



------



### debian12更换镜像源



**备份sources.list**

```bash
cp /etc/apt/sources.list /etc/apt/sources.list.bak  #这一步可以不要
```

**编辑sources.list**

```bash
vi /etc/apt/sources.list
```

**直接输入ggdG,清空信息源**

```bash
ggdG
```

**阿里云镜像站**

```bash
deb https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb-src https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
```

**腾讯云镜像站**

```bash
deb https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb-src https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
```

**网易镜像站**

```bash
deb https://mirrors.163.com/debian/ bookworm main non-free non-free-firmware contrib
deb-src https://mirrors.163.com/debian/ bookworm main non-free non-free-firmware contrib
deb https://mirrors.163.com/debian-security/ bookworm-security main
deb-src https://mirrors.163.com/debian-security/ bookworm-security main
deb https://mirrors.163.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb-src https://mirrors.163.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb https://mirrors.163.com/debian/ bookworm-backports main non-free non-free-firmware contrib
deb-src https://mirrors.163.com/debian/ bookworm-backports main non-free non-free-firmware contrib
```

**华为镜像站**

```bash
deb https://mirrors.huaweicloud.com/debian/ bookworm main non-free non-free-firmware contrib
deb-src https://mirrors.huaweicloud.com/debian/ bookworm main non-free non-free-firmware contrib
deb https://mirrors.huaweicloud.com/debian-security/ bookworm-security main
deb-src https://mirrors.huaweicloud.com/debian-security/ bookworm-security main
deb https://mirrors.huaweicloud.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb-src https://mirrors.huaweicloud.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb https://mirrors.huaweicloud.com/debian/ bookworm-backports main non-free non-free-firmware contrib
deb-src https://mirrors.huaweicloud.com/debian/ bookworm-backports main non-free non-free-firmware contrib
```

**清华大学镜像站**

```bash
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm main contrib non-free non-free-firmware
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm main contrib non-free non-free-firmware
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm-updates main contrib non-free non-free-firmware
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm-updates main contrib non-free non-free-firmware
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm-backports main contrib non-free non-free-firmware
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bookworm-backports main contrib non-free non-free-firmware
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security bookworm-security main contrib non-free non-free-firmware
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security bookworm-security main contrib non-free non-free-firmware
```

**中科大镜像站****

```bash
deb https://mirrors.ustc.edu.cn/debian/ bookworm main contrib non-free non-free-firmware
deb-src https://mirrors.ustc.edu.cn/debian/ bookworm main contrib non-free non-free-firmware
deb https://mirrors.ustc.edu.cn/debian/ bookworm-updates main contrib non-free non-free-firmware
deb-src https://mirrors.ustc.edu.cn/debian/ bookworm-updates main contrib non-free non-free-firmware
deb https://mirrors.ustc.edu.cn/debian/ bookworm-backports main contrib non-free non-free-firmware
deb-src https://mirrors.ustc.edu.cn/debian/ bookworm-backports main contrib non-free non-free-firmware
deb https://mirrors.ustc.edu.cn/debian-security/ bookworm-security main contrib non-free non-free-firmware
deb-src https://mirrors.ustc.edu.cn/debian-security/ bookworm-security main contrib non-free non-free-firmware
```

**更新索引**

```bash
 sudo apt-get update 
```



------



### Debian开启root登录

若您想开启root登录，（不建议）可以按照以下步骤进行操作：
1.打开SSH配置文件，可以使用nano或vim等文本编辑器：

```bash
sudo vim /etc/ssh/sshd_config
```

2.找到包含"PermitRootLogin"的行。该行可能以'#'符号开头进行了注释。如果没有被注释掉，可能的值是"yes"或"prohibit-password"。

3.修改该行的值为"yes"，即：

```bash
PermitRootLogin yes
```

<img src="C:\Users\Administrator\Desktop\2024-02-13_221602.jpg" alt="2024-02-13_221602" style="zoom:50%;" />

4.保存更改并退出文本编辑器。

5.重新启动SSH服务以应用新的配置：

```bash
sudo service ssh restart
```

这样，root登录将被启用，并且用户将可以使用root账户登录到服务器。请注意，使用root账户登录存在一定的安全风险，因此应谨慎使用，并确保设置了强密码来保护root账户的安全。



------



### 在 Debian 上安装 Docker

**1.卸载旧版本**
在安装 Docker Engine 之前，您需要卸载所有冲突的软件包。

Distro 维护者在其存储库中提供 Docker 软件包的非官方发行版。您必须先卸载这些软件包，然后才能安装正式版的 Docker Engine。

要卸载的非官方软件包有：

docker.io
docker-compose
docker-doc
podman-docker
此外，Docker Engine 依赖于containerd和runc。Docker 引擎将这些依赖项捆绑为一个捆绑包：containerd.io. 如果您之前安装过containerd或runc，请卸载它们以避免与 Docker Engine 捆绑的版本冲突。

运行以下命令卸载所有冲突的包：

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

apt-get可能会报告您没有安装这些软件包。

/var/lib/docker/卸载 Docker 时，不会自动删除存储的映像、容器、卷和网络。如果您想从全新安装开始，并且希望清理任何现有数据，请阅读 卸载 Docker 引擎部分。
**2.安装方法**
您可以根据需要以不同的方式安装 Docker Engine：

- Docker Engine 与Linux 版 Docker Desktop捆绑在一起 。这是最简单、最快的入门方法。
- 从Dockerapt存储库设置并安装 Docker 引擎 。
- 手动安装并手动管理升级。
- 使用方便 的脚本。仅建议用于测试和开发环境。

**3.使用 apt 存储库安装**
在新主机上首次安装 Docker Engine 之前，需要设置 Dockerapt存储库。之后，您可以从存储库安装和更新 Docker。

设置 Docker 的apt存储库。

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

> 笔记如果您使用衍生发行版，例如 Kali Linux，您可能需要替换此命令中预期打印版本代号的部分：$(. /etc/os-release && echo "$VERSION_CODENAME")将这部分替换为相应 Debian 版本的代号，例如bookworm

**安装 Docker 软件包。**
要安装最新版本，请运行：

```bash
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

**通过运行镜像验证安装是否成功hello-world ：**

```bash
$ sudo docker run hello-world
```

此命令下载测试映像并在容器中运行它。当容器运行时，它会打印一条确认消息并退出。
您现在已经成功安装并启动了 Docker Engine。

**一键安装docker脚本（以下方法来自官网，未测试）**

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```

**将当前用户加入到docker用户组中，就有了执行docker命令的权限**

```bash
sudo groupadd docker #添加docker用户组，已有用户组可以不创建
sudo usermod -aG docker $USER  #将登陆用户加入到docker用户组中
newgrp docker #更新用户组
docker images    #测试docker命令是否可以使用sudo正常使用
```



------



### Docker 更换配置国内镜像

创建或修改 /etc/docker/daemon.json 文件（json格式一定要正确）

```json
{
    "registry-mirrors": [
        "https://registry.cn-hangzhou.aliyuncs.com",
        "https://docker.nju.edu.cn",
        "https://0hnowjn7.mirror.aliyuncs.com",
        "https://mirror.ccs.tencentyun.com",
        "https://dockerhub.azk8s.com"
    ]
}
```

> DockerHub下载镜像：2023.6.20推荐 南京大学！！！（来源于 我不是矿神）↓
> 阿里云（杭州）   https://registry.cn-hangzhou.aliyuncs.com
> 阿里云（上海）   https://registry.cn-shanghai.aliyuncs.com
> 阿里云（青岛）   https://registry.cn-qingdao.aliyuncs.com
> 阿里云（北京）   https://registry.cn-beijing.aliyuncs.com
> 阿里云（张家口）   https://registry.cn-zhangjiakou.aliyuncs.com
> 阿里云（呼和浩特）   https://registry.cn-huhehaote.aliyuncs.com
> 阿里云（乌兰察布）   https://registry.cn-wulanchabu.aliyuncs.com
> 阿里云（深圳）   https://registry.cn-shenzhen.aliyuncs.com
> 阿里云（河源）   https://registry.cn-heyuan.aliyuncs.com
> 阿里云（广州）   https://registry.cn-guangzhou.aliyuncs.com
> 阿里云（成都）   https://registry.cn-chengdu.aliyuncs.com
> 腾讯云   https://mirror.ccs.tencentyun.com
> 微软云   https://dockerhub.azk8s.com
> 网易   https://hub-mirror.c.163.com
> 上海交通大学   https://mirror.sjtu.edu.cn/docs/docker-registry
> ❤❤❤南京大学   https://docker.nju.edu.cn
> 道客 DaoCloud   https://f1361db2.m.daocloud.io
> 阿里云（香港）   https://registry.cn-hongkong.aliyuncs.com
> 阿里云（日本-东京）   https://registry.ap-northeast-1.aliyuncs.com
> 阿里云（新加坡）   https://registry.ap-southeast-1.aliyuncs.com
> 阿里云（澳大利亚-悉尼）   https://registry.ap-southeast-2.aliyuncs.com
> 阿里云（马来西亚-吉隆坡）   https://registry.ap-southeast-3.aliyuncs.com
> 阿里云（印度尼西亚-雅加达）   https://registry.ap-southeast-5.aliyuncs.com
> 阿里云（印度-孟买）   https://registry.ap-south-1.aliyuncs.com
> 阿里云（德国-法兰克福）   https://registry.eu-central-1.aliyuncs.com
> 阿里云（英国-伦敦）   https://registry.eu-west-1.aliyuncs.com
> 阿里云（美国西部-硅谷）   https://registry.us-west-1.aliyuncs.com
> 阿里云（美国东部-弗吉尼亚）   https://registry.us-east-1.aliyuncs.com
> 阿里云（阿联酋-迪拜）   https://registry.me-east-1.aliyuncs.com
> 谷歌云   https://gcr.io
> 官方   https://registry.hub.docker.com
> 阿里云（香港）之前的几个都不错，推荐微软云！！！不建议阿里云（镜像可能不全！！！！！！）。

阿里云镜像加速网址：https://0hnowjn7.mirror.aliyuncs.com
修改之后重启 Docker 服务

```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
```

开机自动启动docker

```bash
sudo systemctl enable docker
```

Docker Proxy 镜像加速（具体使用方法参考网站介绍）
https://dockerproxy.com/ 访问网站，填上要拉取的镜像名称，自动生成pull命令，下载速度飞快！



------



### 修改grub2系统选择菜单等待时间

grub2的等待时间由/etc/default/grub中GRUB_TIMEOUT设定

```bash
sudo vim /etc/default/grub
```

GRUB_TIMEOUT=3 配置表明等待3秒，可改为相应的时间。

修改完后须要执行update-grub，使配置生效。

```bash
sudo update-grub
```

重启



------



### docker 安装在线笔记 memos

网址：https://github.com/usememos/memos

```bash
docker run -d --name memos --restart always -p 5230:5230 -v ~/.memos/:/var/opt/memos neosmemo/memos:stable
```



------



### docker一键部署青龙面板

**github网址：**[**https://github.com/whyour/qinglong**](https://github.com/whyour/qinglong)

**下面是官网提供的方法：**

```bash
docker run -dit \
  -v $PWD/ql/data:/ql/data \
  -p 5700:5700 \
  -e QlBaseUrl="/" \
  -e QlPort="5700" \
  --name qinglong \
  --hostname qinglong \
  --restart always \
  whyour/qinglong:latest
```



------



### 在 Debian 上设置 Tailscale

软件包适用于 x86 和 ARM CPU，有 32 位和 64 位版本。

1.添加 Tailscale 的包签名密钥和存储库：

```bash
curl -fsSL https://pkgs.tailscale.com/stable/debian/bookworm.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null
curl -fsSL https://pkgs.tailscale.com/stable/debian/bookworm.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list
```

2.安装Tailscale：

```bash
sudo apt-get update 

sudo apt-get install tailscale
```

3.将您的计算机连接到 Tailscale 网络并在浏览器中进行身份验证：

```bash
sudo tailscale up
```

4.您已连接！

您可以通过运行以下命令找到您的 Tailscale IPv4 地址：

```bash
tailscale ip -4
```

如果您添加的设备是服务器或远程访问设备，您可能需要考虑[禁用密钥过期](https://tailscale.com/kb/1028/key-expiry)，以防止需要定期重新进行身份验证。

5.Debian 版本，请使用 apt-get 卸载：

```bash
sudo apt-get remove tailscale
```



------



### 安装linuxserver/qbittorrent

 **docker 网址：**[**https://hub.docker.com/r/linuxserver/qbittorrent**](https://hub.docker.com/r/linuxserver/qbittorrent)**，里面有更多详细的介绍。**

```bash
docker run -d 
--name=qbittorrent 
-e PUID=1000 
-e PGID=1000 
-e TZ=Asia/Shanghai 
-e WEBUI_PORT=8080 
-p 8080:8080 
-p 6881:6881 
-p 6881:6881/udp 
-v /home/ylh/qbittorrent/config:/config 
-v /home/ylh/qbittorrent/downloads:/downloads 
--restart always 
lscr.io/linuxserver/qbittorrent:latest
```

初始用户名：admin

密码随机设定，可使用下面的命令查看：

```bash
sudo docker logs -f qbittorrent
```



------



### 显示系统信息

（1）软件1

```bash
sudo apt install neofetch #安装软件

neofetch #执行程序
```

（2）如出现错误，不显示内存，在相应报错行将冒号改成中文冒号

```bash
sudo apt install screenfetch #安装软件

screenfetc
h #执行程序
```



------



### 安装samba服务

具体参数见https://hub.docker.com/r/dperson/samba

```bash
sudo docker run -it --name samba -m 512m -p 139:139 -p 445:445 \
    --restart always \
    -v /share:/mount \
    -d dperson/samba -p \
    -u "yangluhai;123456" \
    -g "aio read size = 0" \
    -g "aio write size = 0" \
    -r -s "share;/mount/;yes;no;no;all;yangluhai"
```



------



### 安装nginx的两篇文章

https://blog.csdn.net/weixin_43712023/article/details/113712878

https://blog.csdn.net/qq_19309473/article/details/132751728（下面的内容参考这篇文章）



```bash
docker run --name nginx --restart always -d -p 18080:80 nginx:1.24
```

**docker-compose.yml**

```bash
version: '3'
services:
  nginx:
    image: nginx:1.24                # 镜像`nginx:1.24
    container_name: nginx               # 容器名为'nginx'
    restart: always                    # 指定容器退出后的重启策略为始终重启
    volumes:                            # 数据卷挂载路径设置,将本机目录映射到容器目录
      - "/nginx/conf/nginx.conf:/etc/nginx/nginx.conf"
      - "/nginx/conf/conf.d/default.conf:/etc/nginx/conf.d/default.conf"
      - "/nginx/html:/usr/share/nginx/html"
      - "/nginx/log:/var/log/nginx"
    environment:                        # 设置环境变量,相当于docker run命令中的-e
      TZ: Asia/Shanghai
      LANG: en_US.UTF-8
    ports:                              # 映射端口
      - "18080:80"
```

```bash
mkdir /nginx

mkdir /nginx/conf

mkdir /nginx/conf.d

mkdir /nginx/html

mkdir /nginx/log

touch  /nginx/conf/nginx.conf

touch /nginx/conf/conf.d/default.conf

touch /nginx/html/index.html
```



**nginx.conf**          可道云关于nginx.conf的优化https://docs.kodcloud.com/setup/nginx/

```bash
user  nginx;
worker_processes  1;
 
error_log  /var/log/nginx/error.log warn;
pid        /var/run/nginx.pid;
 
events {
    worker_connections  1024;
}
 
http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;
 
    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';
 
    access_log  /var/log/nginx/access.log  main;
 
    sendfile        on;
    #tcp_nopush     on;
 
    keepalive_timeout  65;
 
    #gzip  on;
 
    # include /etc/nginx/conf.d/*.conf;
 
    server {
        listen       80;
        server_name  petty.icuapi.com; # 服务器地址或绑定域名
 
        #charset koi8-r;
        #access_log  /var/log/nginx/host.access.log  main;
 
 
 
        # =========================================================
        # ================== ↓↓↓↓↓↓ start ↓↓↓↓↓↓ ==================
        # =========================================================
 
        location / {
            root   /usr/share/nginx/html;
            #try_files $uri $uri/ @router;
            index  index.html index.htm;
            try_files $uri $uri/ /index.html; # 解决页面刷新 404 问题
            #proxy_pass http://zhengqingya.gitee.io; # 代理的ip地址和端口号
            #proxy_connect_timeout 600; #代理的连接超时时间（单位：毫秒）
            #proxy_read_timeout 600; #代理的读取资源超时时间（单位：毫秒）
        }
        #location @router {
            #rewrite ^.*$ /index.html last; # 拦截80端口后的所有请求地址到登录页面 -> 相当于后端的拦截器
        #}
 
     #   location ^~ /api {  # ^~/api/表示匹配前缀为api的请求
     #       proxy_pass  http://www.zhengqingya.com:5000/api/;  # 注：proxy_pass的结尾有/， -> 效果：会在请求时将/api/*后面的路径直接拼接到后面
#
     #       #  proxy_set_header作用：设置发送到后端服务器(上面proxy_pass)的请求头值
     #       #   【当Host设置为 $http_host 时，则不改变请求头的值;
     #       #     当Host设置为 $proxy_host 时，则会重新设置请求头中的Host信息;
     #       #     当为$host变量时，它的值在请求包含Host请求头时为Host字段的值，在请求未携带Host请求头时为虚拟主机的主域名;
     #       #     当为$host:$proxy_port时，即携带端口发送 ex: $host:8080 】
     #       proxy_set_header Host $host;
#
     #       proxy_set_header X-Real-IP $remote_addr; # 在web服务器端获得用户的真实ip 需配置条件①    【 $remote_addr值 = 用户ip 】
     #       proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;# 在web服务器端获得用户的真实ip 需配置条件②
     #       proxy_set_header REMOTE-HOST $remote_addr;
     #       # proxy_set_header X-Forwarded-For $http_x_forwarded_for; # $http_x_forwarded_for变量 = X-Forwarded-For变量
     #   }
 
     #   location ^~ /blog/ {
     #       proxy_pass  http://zhengqingya.gitee.io/blog/;  # ^~/blog/表示匹配前缀是blog的请求，proxy_pass的结尾有/， 则会把/blog/*后面的路径直接拼接到后面，即移除blog
#
     #       proxy_set_header Host $proxy_host; # 改变请求头值 -> 转发到码云才会成功
     #       proxy_set_header  X-Real-IP  $remote_addr;
     #       proxy_set_header  X-Forwarded-For $proxy_add_x_forwarded_for;
     #       proxy_set_header X-NginX-Proxy true;
     #   }
 
 
        # =========================================================
        # ================== ↑↑↑↑↑↑ end ↑↑↑↑↑↑ ==================
        # =========================================================
 
 
        #error_page  404              /404.html;
 
        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   /usr/share/nginx/html;
        }
    }
}
```

**default.conf**

```bash
server {
  listen       80;
  server_name  localhost;
 
  #charset koi8-r;
  #access_log  /var/log/nginx/host.access.log  main;
 
  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
  }
 
  #error_page  404              /404.html;
 
  # redirect server error pages to the static page /50x.html
  #
  error_page   500 502 503 504  /50x.html;
  location = /50x.html {
    root   /usr/share/nginx/html;
  }
  # proxy the PHP scripts to Apache listening on 127.0.0.1:80
  #
  #location ~ \.php$ {
  #    proxy_pass   http://127.0.0.1;
  #}
  # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
  #
  #location ~ \.php$ {
  #    root           html;
  #    fastcgi_pass   127.0.0.1:9000;
  #    fastcgi_index  index.php;
  #    fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
  #    include        fastcgi_params;
  #}
 
  # deny access to .htaccess files, if Apache's document root
  # concurs with nginx's one
  #
  #location ~ /\.ht {
  #    deny  all;
  #}
}
```

**index.html**

```bash
<!DOCTYPE html>
<html>
<head>
    <title>Welcome to nginx!</title>
    <style>
        body {
            width: 35em;
            margin: 0 auto;
            font-family: Tahoma, Verdana, Arial, sans-serif;
        }
    </style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.</p>
 
<p>For online documentation and support please refer to
    <a href="http://nginx.org/">nginx.org</a>.<br/>
    Commercial support is available at
    <a href="http://nginx.com/">nginx.com</a>.</p>
 
<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

