# better-cloudflare-ip

fork 自 better-cloudflare-ip （https://github.com/badafans/better-cloudflare-ip） 仅供自用，此处代码已作修改，并不适合其他人

## Linux版本

linux shell脚本，自动化筛选

具体使用流程，需要编译里面 fping 4.2 修改版本，另外需要系统安装curl支持。

下载修改过的源码 fping-4.2.tar.gz  点击下载[Linux源码](https://proxy.freecdn.workers.dev/?url=https://github.com/badafans/better-cloudflare-ip/releases/latest/download/linux.tar.gz)

具体编译使用流程如下
 
 ```bash
curl https://github.com/badafans/better-cloudflare-ip/releases/latest/download/linux.tar.gz -o linux.tar.gz

tar -vxf linux.tar.gz

cd linux

./configure

make

cd src

sudo ./cf.sh
```

1.根据你当前带宽设置一个期望的CF速度的大小，比如说家里宽带100兆，如果想要CF单线程下载速度达到20兆的宽带效果，直接输入数值 20 并按回车键

2.等待程序全自动测试结束，找到符合条件的 IP 会在控制台窗口里面输出结果

3.如果你当前网络环境非常差，建议调低期望的带宽值，不然程序会一直停留在查找筛选的过程中

4.外置的 anycast ip 数量根据现有可用路由动态调整，每次测试提取其中的1280分之1，运气好的话五十多秒钟就能获取到自己想要的优选 IP

## Windows版本

windows批处理全自动无门槛操作，自动化筛选

fping-4.2 for win32 修改版（基于 msys2.0 修改编译）点击下载[Windows版本](https://proxy.freecdn.workers.dev/?url=https://github.com/badafans/better-cloudflare-ip/releases/latest/download/windows.zip)

1.解压后运行 CF优选IP.bat 批处理文件（可能需要管理员权限运行，对于 Windows 7 用户或者 cmd 命令行里面不支持curl命令的，需要先解压curl.exe到当前目录）

2.根据你当前带宽设置一个期望的CF速度的大小，比如说家里宽带100兆，如果想要CF单线程下载速度达到20兆的宽带效果，直接输入数值 20 并按回车键

3.等待程序全自动测试结束，找到符合条件的 IP 会在控制台窗口里面输出结果（可以结合里面的单IP测速的批处理来做校验测试）

4.如果你当前网络环境非常差，建议调低期望的带宽值，不然程序会一直停留在查找筛选的过程中

5.外置的 anycast ip 数量根据现有可用路由动态调整，每次测试提取其中的1280分之1，运气好的话一分多钟就能获取到自己想要的优选 IP


## 引用声明

其中 fping 是基于 GitHub 开源项目 https://github.com/schweikert/fping  4.2发行版修改而来，所有脚本均为本人原创内容，转载请注明出处！

对于 Cloudflare Anycast 节点汇总，均为本人扫描 Cloudflare 公开节点汇总而来，Cloudflare IP Ranges 来自 https://www.cloudflare.com/zh-cn/ips/
