# ecommerce-Universal password bypasses login verification(sqli)
## Description
    There is a SQL injection permission bypass vulnerability in the /ecommerce/admin/login.php interface of the commerce website.
## source code
    https://www.sourcecodester.com/php/13524/e-commerce-system-using-phpmysqli.html
## Author
    yangfan2@webray.com.cn inc  
## Proof of Concept
1. Page returned after entering incorrect password

```
POST /ecommerce/admin/login.php HTTP/1.1
Host: 172.20.10.166:8080
Content-Length: 41
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://172.20.10.166:8080
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,imag	e/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://172.20.10.166:8080/ecommerce/admin/login.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=g4gppk342k4t3gn6dlmav29rr0
x-forwarded-for: 127.0.0.1
x-originating-ip: 127.0.0.1
x-remote-ip: 127.0.0.1
x-remote-addr: 127.0.0.1
Connection: close

user_email=janobe&user_pass=123&btnLogin=
```

| ![](E:\Desktop\webRay\cve挖掘\cve提交\ecommerce-Universal password bypasses login verification.assets\image-20240822152914482.png) |
| ------------------------------------------------------------ |



2. Enter the correct password to return to the page

```
POST /ecommerce/admin/login.php HTTP/1.1
Host: 172.20.10.166:8080
Content-Length: 43
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://172.20.10.166:8080
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,imag	e/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://172.20.10.166:8080/ecommerce/admin/login.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=g4gppk342k4t3gn6dlmav29rr0
x-forwarded-for: 127.0.0.1
x-originating-ip: 127.0.0.1
x-remote-ip: 127.0.0.1
x-remote-addr: 127.0.0.1
Connection: close

user_email=janobe&user_pass=admin&btnLogin=
```

| ![image-20240822161628961](https://raw.githubusercontent.com/0xffaaa/cve/main/ecommerce-Universal%20password%20bypasses%20login%20verification.assets/image-20240822161628961.png) |
| ------------------------------------------------------------ |

3. Bypassing permission verification through sql injection

| ![](https://raw.githubusercontent.com/0xffaaa/cve/main/ecommerce-Universal%20password%20bypasses%20login%20verification.assets/image-20240822153239132.png) |
| ------------------------------------------------------------ |

