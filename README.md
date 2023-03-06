# zsh_configure

## 安装
sudo apt-get install zsh

git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh

cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

## or use my zsh configure
git clone https://github.com/mojf3/zsh_configure.git

cp ./zsh_configure/.zshrc ~/

### 更改默认shell
chsh -s /bin/zsh OR chsh -s /usr/bin/zsh

### 然后注销并重新登录

# autojump插件: 目录间快速跳转
### 安装
git clone https://github.com/wting/autojump.git
进入目录

./install.py
### 命令
j xxx

# zsh-syntax-highlighting 高亮插件
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions 输入命令时，会给出建议的命令（灰色部分）按键盘 → 补全
或者自定义补全键，在~/.zshrc文件中添加

bindkey ',' autosuggest-accept

### 安装
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

# git-open:在终端里打开当前项目的远程仓库地址
### 安装
git clone https://github.com/paulirish/git-open.git $ZSH_CUSTOM/plugins/git-open

# git 插件(默认安装了): 可以使用各种 git 命令缩写
git add --all ===> gaa

git commit -m ===> gcmsg

### 查看所有git命令缩写
cat ~/.oh-my-zsh/plugins/git/git.plugin.zsh

# history 命令查看历史输入命令的时间展示格式
### 在~/.zshrc文件中添加
HIST_STAMPS="yyyy-mm-dd"

# 为WSL2配置代理
### 在~/.zshrc文件中添加
export hostip=$(cat /etc/resolv.conf |grep -oP '(?<=nameserver\ ).*')

alias setss='export all_proxy="socks5://${hostip}:7890";'

alias unsetss='unset all_proxy'

### 验证是否代理成功
curl google.com
#### 失败会显示connection timed out

# 解决vim中文乱码问题
### 打开配置文件
vim /usr/share/vim/vimrc

### 添加
set fileencodings=utf-8,gb2312,gbk,gb18030

set termencoding=utf-8

set fileformats=unix

set encoding=prc

# 参考
（插件）https://juejin.cn/post/6844903598300610568

https://zhuanlan.zhihu.com/p/58073103

（插件）https://hufangyun.com/2017/zsh-plugin/

(代理相关) https://solidspoon.xyz/2021/02/17/%E9%85%8D%E7%BD%AEWSL2%E4%BD%BF%E7%94%A8Windows%E4%BB%A3%E7%90%86%E4%B8%8A%E7%BD%91/

（中文乱码）https://blog.51cto.com/u_64214/5588894
