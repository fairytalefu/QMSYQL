# Qt5.9.3安装mysql的QMYSQL驱动
## 1.Question
##### QSqlDatabase: MYSQL driver not loaded.
##### QSqlDatabase: available drivers: QSQLITE QMYSQL QMYSQL3 QODBC QODBC3 QPSQL QPSQL7
## 2.编译安装mysql驱动 
##### sudo apt install libmysqlclient20 libmysqlclient-dev
##### sudo ln -s /usr/lib/x86_64-linux-gnu/libmysqlclient.so /usr/lib/x86_64-linux-gnu/libmysqlclient_r.so 
## 3.在../sqldriver/新建qtsqldrivers-config.pri
## 4.进入qt源码路径下的mysql目录    
##### $QTDIR/Qt5.9.0/5.9/Src/qtbase/src/plugins/sqldrivers/mysql    
## 5.qmake 编译该工程    
##### qmake "INCLUDEPATH+=/usr/include/mysql" "LIBS+=-L/usr/lib/x86_64-linux-gnu/ -lmysqlclient" mysql.pro    
## 6.make && make install    
## 7.如果编译时报错：Project ERROR: Library 'mysql' is not defined. 
##### 把mysql.pro中的 QMAKE_USE += mysql用#注释掉

