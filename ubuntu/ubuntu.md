# ubuntu教程
经常卡死的解决方案
通过输入一段不断释放内存的脚本来进行的操作

https://blog.csdn.net/u010746357/article/details/81813739
通过内存的角度解决的

https://blog.csdn.net/hautxuhaihu/article/details/78924926
1.可能等待几分钟，系统会自动反应过来。你可以选择等待几分钟尴尬。

2.绝大多数情况系统是不会反应过来的，这时候可以进入tty终端直接注销用户。

(1)Ubuntu有6个tty终端，按住Ctrl+Alt+F1可以进入tty1终端，（同理Ctrl+Alt+F2，F3等可以进入其他的tty1终端，这里我们只需要进入一个tty终端就能解决问题）。

(2)进入tty终端后先输入你的用户名和密码登录。

(3)执行命令注销桌面重新登陆：

sudo pkill Xorg    或者 sudo restart  lightdm

https://blog.csdn.net/u010746357/article/details/81813739
