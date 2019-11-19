## oh my zsh 
+ [安装](#az1) 
+ [配置](#pz1) 
	+ [美化](#mh1) 
	+ [插件](#cj1) 
+ [使用](#sy1) 



### 安装
+ <A name="az1"> 安装 </A>  

```
sudo apt install zsh
```

自动安装
制动安装的坏处是很多地方要直接手懂去配置 还要去
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

```
执行这个命令还不如直接从github上下载一步到位

```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```
使用github安装 
然后 chsh -s /bin/zsh  改变当前用户的shell为zsh 可以使用$SHELL查看
修改 root用户可以打开 文件/etc/passwd  将第一行的那个root用户 /bin/bash改成/bin/zsh就可以啦 
+ <A name="pz1"> 配置 </A>  

zsh安装过后用户目录在.oh-my-zsh目录下 
```
LICENSE.txt  cache        lib          oh-my-zsh.sh templates    tools
README.md    custom       log              plugins      themes 
```
如上是目录主要就是要自动插件都是在plugins下面 这里都是一些默认插件 如果要自己下载插件也要放在里面   themes中是默认的主题

配置文件是在  .zshrc中   
+ 找到 ZSH_THEME 哪一个变量后面的=可以是前面themes中的任意一种主题都可以 注意=前后不能有空格
+ 找到plugin(git) 哪一行可以向括号中添加插件 插件之间用空格隔开就可以了  

修改之后使用命令 source ~/.zshrc 就可以啦

 <A name="mh1"> 美化 </A>  

美化基本上就是换换主题  
[官方主题](https://github.com/robbyrussell/oh-my-zsh/wiki/themes) 

其实比较喜欢agnoster 但是会有符号的乱码情况 就不知道咋办了[解决办法](https://github.com/agnoster/agnoster-zsh-theme)


-----------------------------------------------------







+ wget https://raw.githubusercontent.com/powerline/powerline/develop/font/10-powerline-symbols.conf
+ wget https://raw.githubusercontent.com/powerline/powerline/develop/font/PowerlineSymbols.otf
+ sudo mkdir /usr/share/fonts/OTF

+ sudo cp 10-powerline-symbols.conf /usr/share/fonts/OTF/

+ sudo mv 10-powerline-symbols.conf /etc/fonts/conf.d/

+ sudo mv PowerlineSymbols.otf /usr/share/fonts/OTF/



现在使用的是macovsky-ruby 比较简洁也不错


 <A name="cj1"> 插件 </A>


		插件分为两种  一种是 oh my zsh 集成的插件  直接在 plugin(git)中添加就可以了  如我的插件目录   plugins=(git last-working-dir z extract web-search zsh-syntax-highlighting zsh-autosuggestions) 可以看出来插件之间用空格可开隔开就好了
		另一种是野生插件如一些github上好用的插件但是没有在oh my zsh的集成中我们就可以直接使用命令
		```
		git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
		```
将要下载的插件名字替换既可以了  然后再在plugins()中计加入我们的插件就可以了

+ <A name="sy1"> 使用 </A>  

   使用也分为两种  
	本身功能的时候
+ 目录浏览和跳转：输入 d，即可列出你在这个会话里访问的目录列表，输入列表前的序号，即可直接跳转。

+ 在当前目录下输入 .. 或 … ，或直接输入当前目录名都可以跳转，你甚至不再需要输入 cd 命令了。
还有alias
```
200~alias cls='clear'
alias ll='ls -l'
alias la='ls -a'
alias grep="grep --color=auto"
alias -s html='vim' # 在命令行直接输入后缀为 html 的文件名，会在 Vim 中打开
alias -s rb='vim' # 在命令行直接输入 ruby 文件，会在 Vim 中打开
alias -s py='vim' # 在命令行直接输入 python 文件，会用 vim 中打开，以下类似
alias -s js='vim'
alias -s c='vim'
alias -s java='vim'
alias -s txt='vim'
alias -s gz='tar -xzvf' # 在命令行直接输入后缀为 gz 的文件名，会自动解压打开
alias -s tgz='tar -xzvf'
alias -s zip='unzip'
alias -s bz2='tar -xjvf
```
自己研究比较有意思呢 
	插件功能的使用    如  
+ last-working-dir 每次打开进入上一次关
闭的文件夹 
+ z 模糊跳转文件夹
+ extract是一个解压插件直接x djf.zip dsd.tar.gz 之类的   
+ web-search是一个搜索的网页插件 支持google 和 baidu    想搜索什么 直接命令行 baidu 什么就ok 
+ zsh-syntax-highlinghting是语法高亮  
+ zsh-autosuggestions 提供的隐形提示功能

