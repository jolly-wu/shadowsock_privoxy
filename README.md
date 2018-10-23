#mac终端代理方式(shadowsocks+privoxy)
1. 安装ShadowsocksX-NG

2. 配置下面的shadowsocks自带的privoxy配置文件
/Users/$userName/Library/Application Support/ShadowsocksX-NG/privoxy.config
添加以下2项:
listen-address 127.0.0.1:1087   (监听地址)
forward-socks5 / 127.0.0.1:1086 .  (sock5转发监听)

3. 配置~/.bash_profile的代理地址:端口,添加以下2项:
 
export http_proxy='http://127.0.0.1:1087'
export https_proxy='http://127.0.0.1:1087'


4. 测试终端是否代理成功

在终端输入curl ip.cn，如返回‘当前 IP：103.88.46.11 来自：日本 CatNetworks’类似的不在国内的地址则成功了。
