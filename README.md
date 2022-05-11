# zsh_configure

git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh

cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

## 更改默认shell
chsh -s /bin/zsh

# autojump插件: 目录间快速跳转
## 安装
git clone git://github.com/joelthelion/autojump.git

进入目录

./install.py
## 命令
j xxx

# zsh-syntax-highlighting 高亮插件
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions 输入命令时，会给出建议的命令（灰色部分）按键盘 → 补全
或者自定义补全键，在~/.zshrc文件中添加

bindkey ',' autosuggest-accept

## 安装
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions


# git 插件: 可以使用各种 git 命令缩写
git add --all ===> gaa

git commit -m ===> gcmsg

## 查看所有git命令缩写
cat ~/.oh-my-zsh/plugins/git/git.plugin.zsh


# 为WSL2配置代理
export hostip=$(cat /etc/resolv.conf |grep -oP '(?<=nameserver\ ).*')

alias setss='export all_proxy="socks5://${hostip}:7890";'

alias unsetss='unset all_proxy'

## 验证是否代理成功
curl google.com

# 参考
https://juejin.cn/post/6844903598300610568

https://zhuanlan.zhihu.com/p/58073103

https://hufangyun.com/2017/zsh-plugin/

https://solidspoon.xyz/2021/02/17/%E9%85%8D%E7%BD%AEWSL2%E4%BD%BF%E7%94%A8Windows%E4%BB%A3%E7%90%86%E4%B8%8A%E7%BD%91/

