## 一、目录

```

```

## 二、特性

```
1.多站点
2.多url匹配
3.http自动跳转https
4.nginx服务器配置文件范式，方便做自动化
```

## 三、快速开始

### 1.编译安装

### 2.初始配置

### 3.添加站点

```bash
$ cd /etc/nginx/conf.d
```

* Creating a new site
```bash
$ cp templates/example.com.conf .actual-hostname.conf
$ sed -i 's/example.com/actual-hostname/g' .actual-hostname.conf
```

* Enabling a site
```bash
$ mv .actual-hostname.conf actual-hostname.conf
```
	
* Disabling a site
```bash
$ mv actual-hostname.conf .actual-hostname.conf
```

```bash
$ nginx reload
```

### 4.配置url地址匹配

```

```
