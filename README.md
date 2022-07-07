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
