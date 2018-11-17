# nginx-anzhuang
1.安装gcc gcc-c++(如新环境,未安装请先安装)
$ yum install -y gcc gcc-c++
2.安装wget
$ yum -y install wget

3.安装PCRE库
$ cd /usr/local/
$ wget http://jaist.dl.sourceforge.net/project/pcre/pcre/8.33/pcre-8.33.tar.gz
$ tar -zxvf pcre-8.33.tar.gz
$ cd pcre-8.33
$ ./configure
$ make && make install
如果报错:

在 linux 中执行 wget 命令提示 -bash: wget: command not found 解决方法
解决办法 yum -y install wget


5.安装SSL库
$ cd /usr/local/
$ wget http://www.openssl.org/source/openssl-1.0.1j.tar.gz
$ tar -zxvf openssl-1.0.1j.tar.gz
$ cd openssl-1.0.1j
$ ./config
$ make && make install

6.安装zlib库存

$ cd /usr/local/
$ wget http://zlib.net/zlib-1.2.11.tar.gz
$ tar -zxvf zlib-1.2.11.tar.gz
$ ./configure
$ make && make install

5.安装nginx
$ cd /usr/local/
$ wget http://nginx.org/download/nginx-1.8.0.tar.gz
$ tar -zxvf nginx-1.8.0.tar.gz
$ cd nginx-1.8.0 
$ ./configure
$ make && make install

6.启动nginx
cd /usr/local/nginx/sbin/nginx
./nginx 
4停止nginx
方式1，快速停止：
cd /usr/local/nginx/sbin
./nginx -s stop
此方式相当于先查出nginx进程id再使用kill命令强制杀掉进程。

方式2，完整停止(建议使用)：
cd /usr/local/nginx/sbin
./nginx -s quit
此方式停止步骤是待nginx进程处理任务完毕进行停止。


5重启nginx
方式1，先停止再启动（建议使用）：
对nginx进行重启相当于先停止nginx再启动nginx，即先执行停止命令再执行启动命令。
如下：
./nginx -s quit
./nginx

方式2，重新加载配置文件：
当nginx的配置文件nginx.conf修改后，要想让配置生效需要重启nginx，使用-s reload不用先停止nginx再启动nginx即可将配置信息在nginx中生效，如下：
./nginx -s reload
