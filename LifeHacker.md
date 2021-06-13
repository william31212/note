# 生活駭客

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
* [大陸門號](https://www.kocpc.com.tw/archives/283303)
* curl 配 request-bin 傳檔
    ```bash
    (echo -n '{"payload": "'; <file>; echo '"}') | curl -H "Content-Type: application/json" -d @- <requests-bin url>
    ```