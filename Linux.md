# Linux

## SSH

- 帳密直接登
    ```bash
    sudo apt-get install sshpass
    sshpass -p your_password ssh user@hostname
    ```

- set publickey 設定
    - https://blog.gtwang.org/linux/linux-ssh-public-key-authentication/

- ssh vbox
    :::danger
    error log: `ssh_exchange_identification: read: Connection aborted`
    :::
    - solve: 要把密碼登入打開，即可使用
    - https://ephrain.net/kali-%E9%96%8B%E5%95%9F-kali-linux-%E4%B8%8A%E7%9A%84-ssh-server-%E6%9C%8D%E5%8B%99/

### ssh-reverse turnel

- 反向打ssh-turnel
    - N: 單純連線，不送指令
    - f: 放到背景執行
    - R: Remote port forwarding，遠端port重導向
```sh=
ssh -NfR <remote-port>:localhost:22 <remote-server>
```

- dynamic port forwarding 
    - run on remote machine
        - N 讓指令純建立 tunnel，0.0.0.0 讓所有 IP 都能連到這臺機器
```sh=
ssh -ND 0.0.0.0:<local-port> <user>@<remote-server>
```

- CMD 設定proxy

```
set http_proxy=socks5://<remote-server>:<port>
```

## lcx

- 代理port到公網

## sudo 

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

## Tmux
* attach 其他視窗
    * `tmux -S /tmp/tmux-<num>/default`
* 查
    * https://blog.chh.tw/posts/tmux-terminal-multiplexer/
    * https://hackmd.io/Xxa8sfyAT2inRgkVQ2M6Gw?view
    * http://tmuxcheatsheet.com/

## oh-my-zsh install

```cmd=
sudo apt update
sudo apt upgrade
sudo apt install zsh
sudo apt install git
cat /etc/shells
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
chsh -s /bin/zsh

sudo apt install powerline
sudo apt install fonts-powerline
```

* change Theme(powerlevel9k)
    * `git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k`
    * edit `~/.zshrc`
        ```cmd=
        ZSH_THEME="powerlevel9k/powerlevel9k"
        ```
        ```
        # command line 左邊想顯示的內容
        POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(dir) # <= left prompt 設了 "dir"
        # command line 右邊想顯示的內容
        POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(time) # <= right prompt 設了 "time"
        ```

## Vim

### plugin

* powerline plugin
:::warning
sudo apt install python3-pip
pip3 install –user powerline-status

* add in `.vimrc` 
```cmd
set laststatus=2
set t_Co=256
python3 from powerline.vim import setup as powerline_setup
python3 powerline_setup()
python3 del powerline_setup
```
:::


* `.vimrc`
    ```vim
    syntax on
    set guifont=Consolas:h11
    set nu ts=4 sw=4 sts=4 et ai si cin hls ru t_Co=256
    set mouse=a bs=2 ci nocp ar fencs=utf-8
    set sm mat=0
    filetype plugin indent on
    inoremap {<CR>  {<CR>}<Esc>O
    nnoremap <C-Up> <Up>ddp<Up>
    nnoremap <C-Down> ddp
    set laststatus=2
    set t_Co=256
    python3 from powerline.vim import setup as powerline_setup
    python3 powerline_setup()
    python3 del powerline_setup
    ```
    
* https://blog.gtwang.org/linux/powerline-adds-powerful-statuslines-and-prompts-to-vim-and-bash/


### command
- http://www.vixual.net/blog/archives/234

## Shell-script

- 無窮迴圈

```sh=
while :
do
    # do someting you want
done
```

- 切割字串`substr`
    - 1-index
        `echo ${} | cut -c1-5`

- http://wiki.weithenn.org/cgi-bin/wiki.pl?Script_%E6%8C%87%E4%BB%A4%E6%8A%80%E5%B7%A7



## linux 敏感檔案

- 看port`/proc/net/tcp`
- http://wp.blkstone.me/2018/06/abusing-arbitrary-file-read/#421

## 網路ip

- https://en.ipip.net/
- `traceroute`
- `mtr` ip 
- ntt
- google
    - openflow
    - sdn

## search exploit

```
searchsploit <keyword>
```


## 錄封包

- https://mozillazg.com/2015/05/open-tcpdump-result-with-wireshark-gui.html

### tcpdump
```bash=
sudo tcpdump -i <卡> -w <檔案>

```


## windows 開3389

- https://www.itread01.com/content/1552895939.html


## webshell 
https://www.webshell.cc/4422.html


## shodan

![](https://i.imgur.com/qBAtBQB.png)



## reverse-shell upload file

- upload-file
- https://ironhackers.es/en/cheatsheet/transferir-archivos-post-explotacion-cheatsheet

## pipenv

- https://medium.com/@chihsuan/pipenv-%E6%9B%B4%E7%B0%A1%E5%96%AE-%E6%9B%B4%E5%BF%AB%E9%80%9F%E7%9A%84-python-%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-135a47e504f4


```
union select 1,2,group_concat(schema_name),4 from information_schema.schemata#
```

## hashcat 

* https://xz.aliyun.com/t/4008


## VMware WorkStation 16 pro 黑產 

記得選Pro，不要用Player，Player功能很少
> https://www.vmware.com/tw/products/workstation-pro/faq.html
* Serial-key in Github
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
> [name=halloworld]