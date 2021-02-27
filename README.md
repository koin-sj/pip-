记录下安装python3.8.1过程及pip的使用

1.ubuntu默认带着的python版本不是最新版，因此需要手动安装最新版。
查看python的指向命令： 
ls -l /usr/bin | grep python

2.安装python3.8
   直接使用apt-get安装python3.8失败：apt-get install python3.7
所以最好选用手动安装。
   手动安装步骤：
   步骤1：在python官网找到python-3.8.1.tgz的地址：https://www.python.org/ftp/python/3.8.1/Python-3.8.1.tgz
         所有python版本的地址为：https://www.python.org/ftp/python/ 可以根据所需的版本进行选择。
   步骤2：下载安装包
          wget https://www.python.org/ftp/python/3.8.1/Python-3.8.1.tgz
   步骤3：解压安装包
          tar -zxvf Python-3.8.1.tgz
   步骤4：切换到解压后的目录下
          cd Python-3.8.1
   步骤5：./configure（也可以./configure --prefix=/usr/local/python3.8.1）     
          ./configure 
          或者
          ./configure --prefix=/usr/local/python3.7.1 
          注意：因为pip安装第三方库需要ssl模块，而python默认安装ssl功能是不可用的。(转自：https://blog.csdn.net/a1007720052/article/details/107342695)
               所以，我们可以在这步骤加上--enable-optimizations --with-ssl选项进行编译。
   步骤6：编译make（没有安装make的安装一下）
         make
   步骤7：测试make test(这步骤可以不要，可能会花费很长时间) 
          make test 
   步骤8：安装(sudo) make install
          make install
          
  若步骤5执行的是 ./configure，则安装后可执行文件默认放在/usr /local/bin，库文件默认放在/usr/local/lib，配置文件默认放在/usr/local/include，其它的资源文件放在/usr /local/share。
  
  若步骤5执行的是./configure --prefix=/usr/local/python3.8.1，则可执行文件放在/usr /local/python3.8.1/bin，库文件放在/usr/local/python3.8.1/lib，配置文件放在/usr/local/python3.8.1/include，其它的资源文件放在/usr /local/python3.8.1/share
  
  步骤9：若步骤5执行./configure --prefix=/usr/local/python3.7.1，则需要添加环境变量。步骤5是./configure的跳过此步骤
        添加环境变量：PATH=$PATH:$HOME/bin:/usr/local/python3.8.1/bin
        查看环境变量：echo $PATH
        
将python指向默认的python3.8  细节在：https://blog.csdn.net/u014775723/article/details/85213793
  
          
          
   
              
           
          
          
          
       
   
      




