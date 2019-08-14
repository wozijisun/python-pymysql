首先、需要安装Python包。目前使用的是 3.7 的版本。
使用root用户执行：
yum -y groupinstall "Development tools"
yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel
获取 Python-3.7.0.tgz 的包，进行解压缩。
	进入到 python 解压缩后安装包目录内。依次执行如下操作。
	./configure --preix=/usr/local/bin/python3
	make 
	make install
	创建软链接
	ln -s /usr/local/bin/python3/bin/python3 /usr/bin/python3
	ln -s /usr/local/bin/python3/bin/pip3 /usr/bin/pip3

其次、由于目前不能直接使用pip对相关包的安装，所以，我们需要将对应的包进行下载。
1、需要上传压缩包到目录。例如：packages 需创建。
	 pip3 install asn1crypto-0.24.0.tar.gz && pip3 install pycparser-2.19.tar.gz && pip3 install cffi-1.11.5.tar.gz  && pip3 install idna-2.7.tar.gz && pip3 install six-1.11.0.tar.gz && pip3 install cryptography-2.3.1.tar.gz && pip3 install PyMySQL-0.9.2.tar.gz
2、进入到packages解压缩 tar zxf *.tar.gz
3、按照如下顺序执行

	cd asn1crypto-0.24.0 && python3 setup.py install && cd .. && \
	cd pycparser-2.19 && python3 setup.py install && cd .. && \
	cd cffi-1.11.5 && python3 setup.py install && cd .. && \
	cd idna-2.7 && python3 setup.py install && cd .. && \
	cd six-1.11.0 && python3 setup.py install && cd .. && \
	cd cryptography-2.3.1 && python3 setup.py install && cd .. && \
	cd PyMySQL-0.9.2 && python3 setup.py install 
4、使用 pip3 list 命令进行查看


------------------------------------
增加了安装Flask的运行方式
pip3 install MarkupSafe-1.1.1-cp37-cp37m-manylinux1_x86_64.whl && \
pip3 install Jinja2-2.10.1-py2.py3-none-any.whl && \
pip3 install Werkzeug-0.15.4-py2.py3-none-any.whl && \
pip3 install Click-7.0-py2.py3-none-any.whl && \
pip3 install itsdangerous-1.1.0-py2.py3-none-any.whl && \
pip3 install Flask-1.1.1-py2.py3-none-any.whl
安装调用flask的网关方式
pip3 install uwsgi-2.0.18.tar.gz