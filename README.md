# iptv-ningbo-dianxin
zhejiang iptv for dianxin
自用，参考了hangzhoudianxin的文件内容，又添加了几个来自论坛和自己抓包的数据，截止20241005可以用
抓包时间202301001，默认格式为udpxyd代理地址

1.udpxy代理地址请改成自己的私网地址和端口

2.logo只添加了文件名，具体网络的访问方式请修改成自己的页面

3.频道编号是适配于 http://epg.51zmt.top:8000/ 的节目预告单（部分央视和卫视频道，地方频道他这里没有所以没适配）

udpxy代理地址选用ubuntu

网口1（ens192）为lan，网口2(ens224)连IPTV

docker compose
```
version: "3"
services:
  udpxy:
    container_name: udpxy
    image: agrrh/udpxy:latest
    network_mode: host
    restart: always
    command: -T -a ens192 -p 4022 -m ens224 -c 10
```

