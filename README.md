# V2ray-ws-tls-With-Bt-Panel
使用说明：

1、目前仅测试过CentOS7，其他系统未经测试；

2、前提：VPS上要安装有 宝塔Linux面板，且通过宝塔安装有Nginx；

3、确保需要使用的域名已经解析至VPS；

4、如果通过宝塔部署了要使用的域名的网站，请先开启SSL；如果没有部署要使用域名的网站，脚本会自行配置；

5、使用本脚本即可完成部署；

6、后续计划：调整伪装的静态网站，添加对UUID、内部监听端口、以及伪装路径的修改……



Update：
由于自己用的过程中VMESS出现联网故障，索性尝试了一下VLESS协议，可以顺利联网，索性稍微修改了一下脚本，添加了VLESS协议的部署。


注1：
配合使用 chiakge / Linux-NetSpeed 可以获得更好的加速
~~~
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh
./tcp.sh
~~~
安装V2ray-ws-tls-With-Bt-Panel：
~~~
wget -N --no-check-certificate https://raw.githubusercontent.com/xu5343/V2ray_Bt_Panel./master/v2inst.sh && sh v2inst.sh
~~~

卸载重新安装错误修复记录：
~~~
v2ray link
V2Ray 4.40.1 (V2Fly, a community-driven edition of V2Ray.) Custom (go1.16.5 linux/amd64)
A unified platform for anti-censorship.
2021/08/08 02:45:16 Using config from STDIN
2021/08/08 02:45:16 [Info] main/jsonem: Reading config: stdin: //在此处一直无响应
^C

解决方法：

如果 V2Ray 无法启动，请附上 --test 输出。
/usr/local/bin/v2ray --test --config /usr/local/etc/v2ray/config.json  //请按实际情况修改
~~~
 
写在最后：
网络上有很多已经开发多时，比较稳定的部署脚本了，但是由于并不能快速的满足自己的需求，同时为了能够更加有效的利用VPS的资源，而不仅仅是作为一个梯子，所以就花了点时间，对v2ray进行了一些学习，同时参考了一些成熟的脚本思路，自己写了一个适合自己的脚本。不喜勿喷！

来源:https://github.com/hxlive/V2ray_ws_tls_With_Bt_Panel

-----------------------------------------------
## V2Ray配置教程(新2022-04)
其他安装查看：https://www.xth8013.com/website/blogArticle/detail/182

~~~
bash <(curl -s -L https://git.io/v2ray-setup.sh)
~~~
~~~
bash <(curl -s -L https://git.io/v2rayinstall.sh)
~~~
显示一下信息代表安装成功（可直接用以下配置进行连接）(以下配置在链接时使用)：
~~~
---------- V2Ray 配置信息 -------------
 
 地址 (Address) = 207.148.27.37
 
 端口 (Port) = 8080
 
 用户ID (User ID / UUID) = 20be1f8e-2169-4aa1-843e-5ead4250a9f7
 
 额外ID (Alter Id) = 0
 
 传输协议 (Network) = kcp 伪装类型 (header type) = dtls
  
 ---------- END -------------V2Ray 客户端使用教程: https://git.io/v2ray-client提示: 输入 v2ray url 可生成 vmess URL 链接 / 输入 v2ray qr 可生成二维码链接---------- V2Ray vmess URL / V2RayNG v0.4.1+ / V2RayN v2.1+ / 仅适合部分客户端 -------------vmess://ewoidiI6I*****g==
~~~

~~~
---------- V2Ray 配置信息 -------------
 
 地址 (Address) = 207.148.27.37
 
 端口 (Port) = 8080
 
 用户ID (User ID / UUID) = 20be1f8e-2169-4aa1-843e-5ead4250a9f7
 
 额外ID (Alter Id) = 0
 
 传输协议 (Network) = kcp 伪装类型 (header type) = dtls
 ---------- END -------------
 V2Ray 客户端使用教程: https://git.io/v2ray-client
 提示: 输入 v2ray url 可生成 vmess URL 链接 / 输入 v2ray qr 可生成二维码链接
 ---------- V2Ray vmess URL / V2RayNG v0.4.1+ / V2RayN v2.1+ / 仅适合部分客户端 -------------
 vmess://ewoidiI6I*****g==
~~~

配置文件要注意(建议直接复制安装结果中 vmess://**** 地址，直接导入，避免自己填配置出错)：

~~~
v2ray info 查看 V2Ray 配置信息
v2ray config 修改 V2Ray 配置
v2ray link 生成 V2Ray 配置文件链接
v2ray infolink 生成 V2Ray 配置信息链接
v2ray qr 生成 V2Ray 配置二维码链接
v2ray ss 修改 Shadowsocks 配置
v2ray ssinfo 查看 Shadowsocks 配置信息
v2ray ssqr 生成 Shadowsocks 配置二维码链接
v2ray status 查看 V2Ray 运行状态
v2ray start 启动 V2Ray
v2ray stop 停止 V2Ray
v2ray restart 重启 V2Ray
v2ray log 查看 V2Ray 运行日志
v2ray update 更新 V2Ray
v2ray update.sh 更新 V2Ray 管理脚本
v2ray uninstall 卸载 V2Ray
~~~

客户端下载、安装

----
Windows v2ray客户端：
下载方式一：网盘(直接解压可用)

【v2rayN】：https://cloud.degoo.com/share/f-Vljc2ZjhmcPyHbi5Pw0A 或 https://github.com/xyz690/cloudimg/blob/main/data/v2rayN-3.29.zip

解压【【【点击v2rayN.exe启动】】】

下载方式二：GitHub

客户端：下载v2rayN.zip

【v2rayN.exe Github Releases】 https://github.com/2dust/v2rayN/releases/download/3.29/v2rayN.zip

内核：下载v2ray-windows-64.zip文件

【v2ray-windows-64.zip Github Releases】 https://github.com/v2fly/v2ray-core/releases/download/v4.31.0/v2ray-windows-64.zip

对v2ray-windows-64.zip 和 v2rayN进行解压，然后将 v2rayN 目录下所有文件复制到v2ray-windows-64解压后的目录，即两个下载好的文件需要在同一目录。
