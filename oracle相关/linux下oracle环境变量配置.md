# oracle 环境变量配置

## 下载依赖的库
需要下载的依赖库`instantclient-basic-linux.x64-11.2.0.4.0.zip`
下载地址\
https://www.oracle.com/database/technologies/instant-client/linux-x86-64-downloads.html

## 解压
```bash
mkdir -p /app/oracle
cd /app/oracle
unzip instantclient-basic-linux.x64-11.2.0.4.0.zip 

```
## 安装和设置
```bash
cd instantclient_11_2
sudo yum install libaio
sudo sh -c "echo /app/oracle/instantclient_11_2 > /etc/ld.so.conf.d/oracle-instantclient.conf"
sudo ldconfig
```
## 环境配置
将环境变量加入到配置文件中,执行
```bash
vim /etc/profile
```
将下面代码追加到文件末尾并保存退出
```
export LD_LIBRARY_PATH=/app/oracle/instantclient_11_2:$LD_LIBRARY_PATH
```
执行下面命令使配置生效
```
source /etc/profile
```

***end***