```
hive下载地址:
http://archive.cloudera.com/cdh5/cdh/5/
http://archive.cloudera.com/cdh5/cdh/5/hive-1.1.0-cdh5.7.0.tar.gz
注意hive版本要和hadoop版本对应
```

```
~]# useradd hive
~]# su hive
[hive@hadoop001 ~]$ mkdir software
[hive@hadoop001 ~]$ cd software/
[hive@hadoop001 software]$ wget http://archive.cloudera.com/cdh5/cdh/5/hive-1.1.0-cdh5.7.0.tar.gz
[hive@hadoop001 software]$ mkdir ../app
software]$ tar -zxvf hive-1.1.0-cdh5.7.0.tar.gz -C ../app/
software]$ cd /home/hive/app/
```

```
配置环境变量
/home/hive/app/hive-1.1.0-cdh5.7.0
hive-1.1.0-cdh5.7.0]$ vi ~/.bash_profile

PATH=$PATH:$HOME/.local/bin:$HOME/bin
HIVE_HOME=/home/hive/app/hive-1.1.0-cdh5.7.0
PATH=$HIVE_HOME/bin:$PATH

export PATH

```

```
software]$ wget https://repo1.maven.org/maven2/mysql/mysql-connector-java/5.1.49/mysql-connector-java-5.1.49.jar
software]$ cp mysql-connector-java-5.1.49.jar ../app/hive-1.1.0-cdh5.7.0/lib/
```

```
配置MySQL元数据连接配置
vi hive-site.xml

<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
<configuration>
<property>
        <name>javax.jdo.option.ConnectionURL</name>
        <value>jdbc:mysql://localhost:3306/hive?createDatabaseIfNotExist=true&amp;characterEncoding=UTF-8</value>
</property>
 
<property>
      <name>javax.jdo.option.ConnectionDriverName</name>
        <value>com.mysql.jdbc.Driver</value>
</property>
 
<property>
  <name>javax.jdo.option.ConnectionUserName</name>
    <value>root</value>
</property>
 
<property>
  <name>javax.jdo.option.ConnectionPassword</name>
    <value>root</value>
</property>
</configuration>
```