# 常见命令整理
  
- [ps](#ps)
- [lsof](#lsof)
- [netstat](#netstat)
- [kill](#kill)

---  
## ps  
`ps -aux|grep chat.js`  
用于报告当前系统的进程状态  
>a:显示所有程序  
>u:以用户为主的格式来显示  
>x:显示所有程序，不以终端机来区分  

---  
## lsof  
`lsof -i:8090`  
用于查看你进程开打的文件，打开文件的进程，进程打开的端口(TCP、UDP)。找回/恢复删除的文件。因为lsof命令需要访问核心内存和各种文件，所以需要root用户执行。  
>-a：列出打开文件存在的进程；  
>-c<进程名>：列出指定进程所打开的文件；  
>-g：列出GID号进程详情；  
>-d<文件号>：列出占用该文件号的进程；  
>+d<目录>：列出目录下被打开的文件；  
>+D<目录>：递归列出目录下被打开的文件；  
>-n<目录>：列出使用NFS的文件；  
>-i<条件>：列出符合条件的进程。（4、6、协议、:端口、 @ip ）  
>-p<进程号>：列出指定进程号所打开的文件；  
>-u：列出UID号进程详情；  
>-h：显示帮助信息； 
>-v：显示版本信息。  

---  
## netstat  
`netstat -pan | grep 5623`  
查看端口占用  
>-a或--all：显示所有连线中的Socket；  
>-A<网络类型>或--<网络类型>：列出该网络类型连线中的相关地址；  
>-c或--continuous：持续列出网络状态；  
>-C或--cache：显示路由器配置的快取信息；  
>-e或--extend：显示网络其他相关信息；  
>-F或--fib：显示FIB；  
>-g或--groups：显示多重广播功能群组组员名单；  
>-h或--help：在线帮助；  
>-i或--interfaces：显示网络界面信息表单；  
>-l或--listening：显示监控中的服务器的Socket；  
>-M或--masquerade：显示伪装的网络连线；  
>-n或--numeric：直接使用ip地址，而不通过域名服务器；  
>-N或--netlink或--symbolic：显示网络硬件外围设备的符号连接名称；  
>-o或--timers：显示计时器；  
>-p或--programs：显示正在使用Socket的程序识别码和程序名称；  
>-r或--route：显示Routing Table；  
>-s或--statistice：显示网络工作信息统计表；  
>-t或--tcp：显示TCP传输协议的连线状况；  
>-u或--udp：显示UDP传输协议的连线状况；  
>-v或--verbose：显示指令执行过程；  
>-V或--version：显示版本信息；  
>-w或--raw：显示RAW传输协议的连线状况；  
>-x或--unix：此参数的效果和指定"-A unix"参数相同；  
>--ip或--inet：此参数的效果和指定"-A inet"参数相同。  

---  
## kill
用来删除执行中的程序或工作  
`kill  -9 2078`  
>-a：当处理当前进程时，不限制命令名和进程号的对应关系；  
>-l <信息编号>：若不加<信息编号>选项，则-l参数会列出全部的信息名称；  
>-p：指定kill 命令只打印相关进程的进程号，而不发送任何信号；  
>-s <信息名称或编号>：指定要送出的信息；  
>-u：指定用户。  

*只有第9种信号(SIGKILL)才可以无条件终止进程，其他信号进程都有权利忽略*

>HUP     1    终端断线  
>INT     2    中断（同 Ctrl + C）  
>QUIT    3    退出（同 Ctrl + \）  
>TERM   15    终止  
>KILL    9    强制终止  
>CONT   18    继续（与STOP相反， fg/bg命令）  
>STOP   19    暂停（同 Ctrl + Z）  

---  
## java -jar *.jar
运行jar包
## nohup command &
后台运行
`nohup java -jar test.jar &`  

*&emsp;&emsp;&的意思是在后台运行， 什么意思呢？  意思是说， 当你在执行 `./a.out &` 的时候， 即使你用ctrl C,  那么`a.out`照样运行（因为对SIGINT信号免疫）。 但是要注意， 如果你直接关掉shell后， 那么， `a.out`进程同样消失。 可见， &的后台并不硬（因为对SIGHUP信号不免疫）。  
&emsp;&emsp;nohup的意思是忽略SIGHUP信号， 所以当运行`nohup ./a.out`的时候， 关闭shell, 那么`a.out`进程还是存在的（对SIGHUP信号免疫）。 但是， 要注意， 如果你直接在shell中用Ctrl C, 那么, `a.out`进程也是会消失的（因为对SIGINT信号不免疫）*

- CTRL+Z挂起进程并放入后台  
- jobs 显示当前暂停的进程  
- bg %N 使第N个任务在后台运行(%前有空格)  
- fg %N 使第N个任务在前台运行  

---  
## jar  
`jar -xvf hello.war ` 
将war包解压到当前文件夹  
`jar -cvfM0 hello.war ./ ` 
将当前文件夹下所有内容打成war包  

>x 解包  
>c 打包  
>v 显示过程信息  
>0 这个是阿拉伯数字，只打包不压缩的意思  

---  
## tail
依照要求将指定的文件的最后部分输出到标准设备，通常是终端，通俗讲来，就是把某个档案文件的最后几行显示到终端上，假设该档案有更新，tail会自己主动刷新，确保你看到最新的档案内容。  
`tail -f logs/catalina.out`  
>-f 该参数用于监视File文件增长。  
>-c Number 从 Number 字节位置读取指定文件  
>-n Number 从 Number 行位置读取指定文件。  
>-m Number 从 Number 多字节字符位置读取指定文件，比方你的文件假设包括中文字，假设指定-c参数，可能导致截断，但使用-m则会避免该问题。  
>-b Number 从 Number 表示的512字节块位置读取指定文件。  
>-k Number 从 Number 表示的1KB块位置读取指定文件。  

---  
## 
查看运行进程所在目录  
`ll /proc/PID`  
>cwd符号链接的是进程运行目录；  
>exe符号连接就是执行程序的绝对路径；  
>cmdline就是程序运行时输入的命令行命令；  
>environ记录了进程运行时的环境变量；  
>fd目录下是进程打开或使用的文件的符号连接。  

---  
## tar  
解压.tar.gz  
`tar zxvf pythontab.tar.gz`  

---  
## gzip  
解压.gz  
`gzip -b pythontab.gz`