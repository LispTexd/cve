# payroll-management-system-in-php has sql injection in delete.php

## supplier 
https://code-projects.org/payroll-management-system-in-php-with-source-code/
## Vulnerability parameter
delete.php

## describe

An unrestricted SQL injection attack exists in payroll-management-system in delete.php. The parameters that can be controlled are as follows: $emp_id. This function executes the id parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

**Code analysis**    

When the value of   $overtime parameter is obtained in function , it will be concatenated into SQL statements and executed, which has a SQL injection vulnerability. 

![Image](https://github.com/user-attachments/assets/6c0e87f9-1008-4f5b-923c-b0007121a9e4)



## POC

```
GET /delete.php?emp_id=1 HTTP/1.1
Host: payroll
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.6261.112 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=85u4m47klj7ldjr47mclti8mr6
Connection: close


```

**Result**

get databases 

![image-20241226013405312](https://github.com/user-attachments/assets/fd4a6d5f-7c7d-418d-8db1-2bbd2d5bc9a0)
