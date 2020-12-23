# Windows

## set Proxy

* Command Line
```batch
set http_proxy=socks5://<remote-server>:<port>
```

## `lcx.exe`
* 能夠代理port到公網

## windows 開 3389

```batch
net user <username> <password> /add
```

* 將`user`加到管理員群組
```batch
net localgroup Administrators <username> /add
```

* 開啟 `3389` port
```batch
REG ADD HKLM\SYSTEM\CurrentControlSet\Control\Terminal" "Server /v fDenyTSConnections /t REG_DWORD /d 00000000 /f
```
> Reference：https://www.itread01.com/content/1552895939.html

## Windows Tricks
* windows監控遠端task跟service
    - `sc` `tasklist`
    - https://www.raymond.cc/blog/remotely-start-and-stop-applications-or-services-over-the-internet/
* [送windows通知](http://vaskovsky.net/notify-send/)

## win10 系統密碼 Hack Tool
* netpass
* mimikatz

## `netsh`

* https://charleslin74.pixnet.net/blog/post/441670006-%5Bwindows%5D-%E4%BD%BF%E7%94%A8netsh%E4%BE%86%E9%81%94%E6%88%90port-forwarding

