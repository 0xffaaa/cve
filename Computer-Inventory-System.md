#Computer Inventory System Stored Cross-Site Scripting(XSS)
<br>
#Description
<br>
The system Client doesn't properly sanitise POST parameter, which result into a Stored Cross-Site Scripting(XSS).
<br>
#Vendor Homepage
<br>
https://www.sourcecodester.com/php/17165/computer-inventory-system-using-php-and-mysql-source-code.html
<br>
#Author
<br>wenqin@webray.com.cn inc
#Proof of Concept
<br>
1.Open the website and enter payload at the input title
![Computer-Inventory-System-1.png](../img/Computer-Inventory-System-1.png "1")<br />
2.Visiting the home page of the website will trigger the code
![Computer-Inventory-System-2.png](../img/Computer-Inventory-System-2.png "1")