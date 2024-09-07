# anti-novel-domain
收集的中文小说网站列表，用于做防火墙阻断用。

为防止内部网络中的用户浏览小说网站，收集了一些小说网站域名，用于做防火墙阻断。

## 用法
### 1. OpenWrt + [Simple AdBlock](https://github.com/stangri/openwrt-simple-adblock)
Tested on OpenWrt 22.03

[Doc about Simple AdBlock](https://docs.openwrt.melmac.net/simple-adblock/)

强制重定向DNS查询：

![image](https://github.com/user-attachments/assets/2fcdce9d-4352-46b7-a8aa-9b2a98ec9cb6)

配置要下载文件的URL：

![image](https://github.com/user-attachments/assets/677b3787-9e71-4834-afc4-c1a94cbd8c37)

URL to download the anti-novel-domain file: https://raw.githubusercontent.com/hplc/anti-novol-domain/main/anti-novol-domains.txt
#### 测试
![image](https://github.com/user-attachments/assets/18401b76-6cea-4364-9504-5749eeffda13)

![image](https://github.com/user-attachments/assets/f072e0b9-766e-4132-a221-5ec76550b33c)

### 2. Squid with acl url_regex
Tested on Squid 3.1
```
acl novel_domains url_regex "anti-novel-domains.txt"
http_access deny novel_domains 
```
#### 测试
![image](https://github.com/user-attachments/assets/89d98824-b8fb-4819-a76c-96381ef8312a)

![image](https://github.com/user-attachments/assets/a84558d0-8d57-4511-aee3-eb98242c34fa)


