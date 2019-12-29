## 一、目录

```
.
├── certs
│   ├── default.crt
│   ├── default.key
├── conf.d
│   ├── default.conf
│   ├── no-ssl.default.conf
│   └── templates
│       ├── example.com.conf
│       ├── no-ssl.example.com.conf
│       ├── other.example.com.conf
│       └── www.example.com.conf
├── h5bp
│   ├── basic.conf
│   ├── cross-origin
│   │   ├── requests.conf
│   │   └── resource_timing.conf
│   ├── errors
│   │   └── custom_errors.conf
│   ├── internet_explorer
│   │   └── x-ua-compatible.conf
│   ├── location
│   │   ├── security_file_access.conf
│   │   ├── web_performance_filename-based_cache_busting.conf
│   │   └── web_performance_svgz-compression.conf
│   ├── media_types
│   │   ├── character_encodings.conf
│   │   └── media_types.conf
│   ├── security
│   │   ├── content-security-policy.conf
│   │   ├── referrer-policy.conf
│   │   ├── server_software_information.conf
│   │   ├── strict-transport-security.conf
│   │   ├── x-content-type-options.conf
│   │   ├── x-frame-options.conf
│   │   └── x-xss-protection.conf
│   ├── ssl
│   │   ├── certificate_files.conf
│   │   ├── ocsp_stapling.conf
│   │   ├── policy_deprecated.conf
│   │   ├── policy_intermediate.conf
│   │   ├── policy_modern.conf
│   │   └── ssl_engine.conf
│   └── web_performance
│       ├── cache_expiration.conf
│       ├── cache-file-descriptors.conf
│       ├── compression.conf
│       ├── no-transform.conf
│       ├── pre-compressed_content_brotli.conf
│       └── pre-compressed_content_gzip.conf
├── mime.types
└── nginx.conf
```

## 二、特性

```
1.多站点
.
├── conf.d
│   ├── default.conf
│   ├── no-ssl.default.conf
│   ├── geercode.com.conf
│   ├── www.geercode.com.conf
│   ├── test.geercode.com.conf
│   ├── slb-test.geercode.com.conf
2.多url匹配
3.http自动跳转https
所有对nginx的http请求统一转到https，对应域名不存在则返回444，无法连接
监听一级域名转到二级域名www
4.nginx服务器配置文件范式，方便做自动化
外网域名:test.geercode.com
内网域名:slb-test.geercode.com
```

## 三、快速开始

### 1.编译安装

### 2.初始配置

### 3.添加一级域名

```bash
$ cd /etc/nginx/conf.d
```

* Creating a new site
```bash
$ cp templates/www.example.com.conf actual-hostname.conf
$ sed -i 's/example.com/actual-hostname/g' actual-hostname.conf
```

> eg:
>> cp templates/www.example.com.conf geercode.com.conf
>> sed -i 's/example.com/geercode.com/g' geercode.com.conf
>> nginx -s reload
>> 记得创建目录 /var/www/www.geercode.com/public/index.html

* Disabling a site
```bash
$ mv actual-hostname.conf .actual-hostname.conf
```

* Enabling a site
```bash
$ mv .actual-hostname.conf actual-hostname.conf
```

```bash
$ nginx -s reload
```

> 注意

### 4.添加二级域名

* 
```bash
$ cp templates/other.example.com.conf other.actual-hostname.conf
$ sed -i 's/other.example.com/other.actual-hostname/g' other.actual-hostname.conf
$ nginx -s reload
```

> eg:
>> cp templates/other.example.com.conf test.geercode.com.conf
>> sed -i 's/other.example.com/test.geercode.com/g' test.geercode.com.conf
>> nginx -s reload
>> 记得创建目录 /var/www/test.geercode.com/public/index.html

### 5.配置url地址匹配

```

```
