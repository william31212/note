# Linux_Command

## SSH

- 帳密直接登
```bash
sudo apt-get install sshpass
sshpass -p your_password ssh user@hostname
```

- set `publickey` 設定
    - https://blog.gtwang.org/linux/linux-ssh-public-key-authentication/

- `ssh vbox`
    - Solve: 要把密碼登入打開，即可使用
    - https://ephrain.net/kali-%E9%96%8B%E5%95%9F-kali-linux-%E4%B8%8A%E7%9A%84-ssh-server-%E6%9C%8D%E5%8B%99/

!> **Important** error log: `ssh_exchange_identification: read: Connection aborted`

### ssh-reverse turnel

- 反向打`ssh-turnel`
    - `-N` 單純連線，不送指令
    - `-f` 放到背景執行
    - `-R` Remote port forwarding，遠端port重導向

```bash
ssh -NfR <remote-port>:localhost:22 <remote-server>
```

- dynamic port forwarding
    - run on remote machine
        - N 讓指令純建立 tunnel，0.0.0.0 讓所有 IP 都能連到這臺機器

```bash
ssh -ND 0.0.0.0:<local-port> <user>@<remote-server>
```

## Sudo

* To root
    * `sudo -i`
* To user
    * `sudo -m`
* add sudo group
    * `usermod -aG sudo <user>`

## Crontab

- https://jqnets.com/blog/ubuntu-%E6%8E%92%E7%A8%8B%E8%A8%AD%E5%AE%9A-%EF%BC%9Acrontab-%E6%8E%92%E7%A8%8B%E4%BD%BF%E7%94%A8%E6%95%99%E5%AD%B8/


- crontab -l    列出該使用者擁有的 crontab 指令
- crontab -e   編輯該使用者的 crontab 指令

```
* * * * * <shellscript-pos>
```



### Command
- [Vim 指令大全](http://www.vixual.net/blog/archives/234)

## Shell Script

* [Introduction-to-bash-scripting](https://github.com/bobbyiliev/introduction-to-bash-scripting)

* 無窮迴圈
```bash
while :
do
    # do someting you want
done
```

* 切割字串 `substr`
    - 1-index
        `echo ${} | cut -c1-5`

- 背景執行
```
echo 'Starting Logging Server on Host B...'            //顯示字串
ssh hostb.weithenn.org 'sudo /home/logging.sh' &       //控制遠端主機 B 執行 logging.sh，並丟到背景執行
pid_of_q="$!"                                          //抓取上一行丟到背景執行的 Process ID
sleep 5                                                //休息 5 秒 (不然下一行會砍不掉)
kill -9 ${pid_of_q}                                    //強制砍掉剛才丟到背景執行的 Process ID (當然這時遠端主機 B 的 logging.sh 是有在執行的)
```
> Reference: http://wiki.weithenn.org/cgi-bin/wiki.pl?Script_%E6%8C%87%E4%BB%A4%E6%8A%80%E5%B7%A7

## Linux Sensitive file

- 看 Port `/proc/net/tcp`
- http://wp.blkstone.me/2018/06/abusing-arbitrary-file-read/#421

## Network Related

- https://en.ipip.net/
- `traceroute`
- `mtr` ip
- ntt
- google
    - openflow
    - sdn

## Tcpdump (錄封包)

```bash
sudo tcpdump -i <卡> -w <檔案>
```
> Ref: https://mozillazg.com/2015/05/open-tcpdump-result-with-wireshark-gui.html

## hashcat
* https://xz.aliyun.com/t/4008
