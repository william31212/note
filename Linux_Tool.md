# Linux_Tool

## Tmux
* attach 其他視窗
    * `tmux -S /tmp/tmux-<num>/default`
* 查
    * https://blog.chh.tw/posts/tmux-terminal-multiplexer/
    * https://hackmd.io/Xxa8sfyAT2inRgkVQ2M6Gw?view
    * http://tmuxcheatsheet.com/

## oh-my-zsh install

```bash
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
```bash
sudo apt install python3-pip
pip3 install –user powerline-status
```
* add in `.vimrc`
```bash
set laststatus=2
set t_Co=256
python3 from powerline.vim import setup as powerline_setup
python3 powerline_setup()
python3 del powerline_setup
```


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
