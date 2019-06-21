# 项目说明

源代码构建 Caddy，使用 alidns 插件来获取域名证书。

# 源代码构建

```
SET GO111MODULE=on
go mod init caddy
go get -v github.com/mholt/caddy
go install -v
```

# Caddyfile 样板

```
www.mydomain.com {
	tls {
		dns alidns
		wildcard
	}

	gzip
	log ./access.log

	root ./www.mydomain.com
}
```

# 启动服务器

```
SET ALICLOUD_ACCESS_KEY=KKKKKKKKKKKKKKKK
SET ALICLOUD_SECRET_KEY=SSSSSSSSSSSSSSSSSSSSSSSSSSSSSS
caddy
```

# 参考资料

[源代码构建](https://github.com/mholt/caddy#build)
