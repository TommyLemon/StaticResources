# APIJSON后端极速部署 - Java

### 1.下载后解压

[打开这个项目的GitHub主页](https://github.com/TommyLemon/StaticResources) &gt; Clone or download &gt; [Download ZIP](https://github.com/TommyLemon/StaticResources/archive/master.zip) &gt; 解压到一个路径并记住这个路径。
<br />
其中 jar包文件 和 lib文件夹 必须在同一文件夹下。

<br />

### 2.运行后端工程

请先确保已 [配置 Java 运行环境](https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&rsv_idx=1&tn=baidu&wd=java%20%E7%8E%AF%E5%A2%83&oq=java%2520%25E8%25BF%2590%25E8%25A1%258C%25E7%258E%25AF%25E5%25A2%2583&rsv_pq=d879cd0700028015&rsv_t=657eXMFo1t2RvFyaDhC7V9OFMbKxOzGfNR5YwCGWfqBuY6aD3XAeUPePjlw&rqlang=cn&rsv_enter=1&rsv_sug3=3&rsv_sug1=2&rsv_sug7=100&rsv_sug2=0&inputT=296&rsv_sug4=626)。

#### 直接运行

Windows 或 MacOS 可直接双击 jar 包运行。
运行太快会看不出有反应，可以查看 java 进程：
```
ps -ef|grep java
```

<br />

#### 命令行运行

前台运行：
```
java -jar {替换为所在目录路径}apijson-demo-roleless2.9.3.jar
```

<br />

或 后台运行：
```
nohup java -jar {替换为所在目录路径}apijson-demo-roleless2.9.3.jar > {替换为所在目录路径}apijson_log20181005.txt  &
```
可查看日志：
```
tailf {替换为所在目录路径}apijson_log20181005.txt
```

<br />

<h4>运行后会出现 APIJSON的测试日志，最后显示 "APIJSON已启动" ，说明已启动完成。</h4>

如果是Address already in use，说明8080端口被占用，<br />
可以关闭占用这个端口的程序(可能就是已运行的APIJSON工程) <br />
或者 [使用 APIJSON 源码](https://github.com/TommyLemon/APIJSON/tree/master/APIJSON-Java-Server) 改下APIJSON工程的端口号，参考 [SpringBoot改端口](https://stackoverflow.com/questions/21083170/spring-boot-how-to-configure-port)。<br />
其它问题请谷歌或百度。

<br />

### 3.测试连接<br />
在浏览器输入 [http://localhost:8080/get/{}](http://localhost:8080/get/{}) <br />
如果出现
```json
{
  "code": 200,
  "msg": "success"
}
```
则说明已连接上。<br />

如果是404 Not Found，请把防火墙关闭，以便外网能够访问你的电脑或服务器。<br />
其它问题请谷歌或百度。

<br />

### 4.导入表文件到数据库<h3/>

<h4>可以先跳过，用Table, Column或者其它 你自己数据库中已有的表 来测试。</h4>

后端需要MySQL Server和MySQLWorkbench，没有安装的都先下载安装一个。<br />
我的配置是Windows 7 + MySQL Community Server 5.7.16 + MySQLWorkbench 6.3.7 和 OSX EI Capitan + MySQL Community Server 5.7.16 + MySQLWorkbench 6.3.8 + Postgre 2.1.5，其中系统和软件都是64位的。

#### 使用 Navicat
启动Navicat &gt; 双击 localhost &gt; 双击 postgres &gt; 右键 postgres &gt; <br /> 如果没有 sys 模式则先右键新建一个 &gt; 运行 SQL 文件 &gt; 根据你使用的数据库类型来选择刚才解压路径下的 APIJSON-Master/MySQL 和 APIJSON-Master/PostgreSQL <br />
&gt; 开始 &gt; 右键 postgres 里的 sys &gt; 刷新， sys/表 会出现添加的表。

#### 使用 MySQLWorkbench（仅限MySQL）
启动MySQLWorkbench &gt; 进入一个Connection &gt; 如果没有 sys Schema则先右键新建一个 &gt; 点击Server菜单 &gt; Data Import &gt; 选择刚才解压路径下的APIJSON-Master/MySQL &gt; Start Import &gt; 刷新SCHEMAS， 左下方 sys/tables 会出现添加的表。

<br />

### 5.测试接口<br />
直接使用 [APIJSON在线工具](http://apijson.cn/) 或 下载主页提供的 [客户端App](https://github.com/TommyLemon/APIJSON)。

<br />
