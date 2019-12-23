## Manage sites

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
