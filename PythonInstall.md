
[TOC "float:right"]
#Install Python 2.7.13 in Centos 6.8 x86

##Install Python 2.7.13
```Shell
cd /opt
wget https://www.python.org/ftp/python/2.7.13/Python-2.7.13.tar.xz
unxz Python-2.7.13.tar.xz
tar xvf Python-2.7.13.tar
yum install gcc gcc-c++ zlib* bzip2-devel openssl-devel ncurses-devel -y 
cd /opt/Python-2.7.13
./configure --enable-shared 
make && make install
mv /usr/bin/python /usr/bin/python2.6.6
ln -s /usr/local/bin/python2.7 /usr/bin/python 
   #change "#!/usr/bin/python" to "#!/usr/bin/python2.6.6"
vim /etc/ld.so.conf 
   #add new line: "/usr/local/lib"
/sbin/ldconfig  
/sbin/ldconfig -v
```
## Install Pip
```Shell
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py
whereis pip
ln -s /usr/local/bin/pip2.7 /usr/bin/pip
```
### Install flask
```Shell
pip install flask

```
### Install Flask-Cors
```Shell
pip install Flask-Cors
```

### Install  flask_sqlalchemy
```Shell
pip install flask_sqlalchemy
```
### Install MySQL-python
```Shell
yum install mysql*  mysql-devel -y 
pip install MySQL-python
vim /etc/ld.so.conf
# add new line : "/usr/lib64/mysql/"
ldconfig
ldconfig -v 
```
### Install requests
```Shell
pip install requests

```
### Install gunicorn
```Shell
pip install gunicorn
# nohup gunicorn -w 4 -b 0.0.0.0:Port PythonName:app  -p ./gun.pid &
```


### Install pymysql
```Shell
pip install pymysql
```
## Install Reids Server
```Shell
cd /opt
yum install tcl* -y 
wget http://download.redis.io/releases/redis-3.2.8.tar.gz
tar zxvf redis-3.2.8.tar.gz
cd redis-3.2.8
make
make test 
make install
cp redis.conf /etc/
vim /etc/redis.conf


```