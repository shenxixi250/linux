## shell 课程 第一天

1.  用途
	-  自动化批量系统初始化程序(update,软件安装,安全策略)
	-	自动化批量软件部署程序_(LAMP,LNMP,Tomcat,LVS等)
	-	管理应用软件 (KVM,集群管理扩容,Mysql+)
	-	日志分析处理
	-	自动化备份恢复程序__(Mysql安全备份/增量)
	-	自动化的管理程序(批量修改远程修改密码,软件升级)
	-	自动化采集信息以及监控程序(系统/应用状态.CPu.端口链接状态,tcp,Mem)
	-	自动化扩容(增加云主机===>>业务上线)
			zabbix监控CPU 用到90%以上 python API AWS_(增加主机) + shell script(业务上线)  
 
## shell基础
	一个简单的shell程序  在ping.sh中添加
	``` 
#!/usr/bin/bash
	ping -cl www.baidu.com &> /home/shen/tast && echo "www.baidu.com" is contect||echo"www.baidu.com is dowm" 
	```
这个简单的例子教会了什么  
1.  如何执行这个脚本    bash ping.sh如果没有添加第一行的话就要用我们用命令行来做指定bash来运行  或者当第一行加过了指定运行的shell版本就可以使用 ./ping.sh阿里直接执行了yi
2.  这个程序是什么意思 ping是查询能不能ping通一个网络如果ping通的话就会执行&&(且) 每个命令执行都会都一个返回值这个返回值存储在?中
```
# data 
# echo $?  //当程序正常执行的时候 这个?存的就是 0 这个值了    当程序执行错误的时候就会返回非零值了
```
&&符号是具有逻辑判断能力的  只有前一个命令执行成功也就是?==0  && 才会执行下一个命令也就是echo 提示成功的命令如果失败的或就会执行||后的提示命令了     
3.  这里的&>是输出结果重定向的意思如果没有这个的话就会在我们的shell中出现一些结果提示 这个可能不是我们想要的好有一个  
4.  ;仅仅表示的是命令的链接 并不会对前一条指令做出判断


