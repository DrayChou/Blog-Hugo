---
layout: blog
title: 使用 acme.sh 来更新 letsencrypt 证书
date: 2017-06-21 12:55:52
categories:
- linux
tags:
- letsencrypt
- acme
---

# 1. 安装 **acme.sh**

安装很简单, 一个命令:
```
curl  https://get.acme.sh | sh
```

普通用户和 root 用户都可以安装使用.
安装过程进行了以下几步:

1) 把 acme.sh 安装到你的 **home** 目录下:

```
~/.acme.sh/
```
并创建 一个 bash 的 alias, 方便你的使用:  `acme.sh=~/.acme.sh/acme.sh`

2). 自动为你创建 cronjob,  每天 0:00 点自动检测所有的证书, 如果快过期了, 需要更新, 则会自动更新证书.

更高级的安装选项请参考: https://github.com/Neilpang/acme.sh/wiki/How-to-install

**安装过程不会污染已有的系统任何功能和文件**, 所有的修改都限制在安装目录中: `~/.acme.sh/`

# 2. 生成证书

## 1. dns 方式, 在域名上添加一条 txt 解析记录, 验证域名所有权.

这种方式的好处是, 你不需要任何服务器, 不需要任何公网 ip, 只需要 dns 的解析记录即可完成验证.

```
acme.sh  --issue  --dns   -d mydomain.com
```

然后, **acme.sh** 会生成相应的解析记录显示出来, 你只需要在你的域名管理面板中添加这条 txt 记录即可.

等待解析完成之后, 重新生成证书:
```
acme.sh  --renew   -d mydomain.com
```
注意第二次这里用的是 `--renew`

更详细的 api 用法: https://github.com/Neilpang/acme.sh/blob/master/dnsapi/README.md


# 3. copy/安装 证书

前面证书生成以后, 接下来需要把证书 copy 到真正需要用它的地方.

注意, 默认生成的证书都放在安装目录下: `~/.acme.sh/`,  请不要直接使用此目录下的文件, 例如: 不要直接让 nginx/apache 的配置文件使用这下面的文件. 这里面的文件都是内部使用, 而且目录结构可能会变化.

正确的使用方法是使用 `--installcert` 命令,并指定目标位置, 然后证书文件会被copy到相应的位置,
例如:
```
acme.sh  --installcert  -d  mydomain.com   \
        --key-file   /etc/nginx/ssl/mydomain.key \
        --fullchain-file /etc/nginx/ssl/mydonain.cer \
        --reloadcmd  "service nginx force-reload"
```

(一个小提醒, 这里用的是 `service nginx force-reload`, 不是 `service nginx reload`, 据测试, `reload` 并不会重新加载证书, 所以用的 `force-reload`)

`--installcert`命令可以携带很多参数, 来指定目标文件.  并且可以指定 reloadcmd, 当证书更新以后, reloadcmd会被自动调用,让服务器生效.

详细参数请参考: https://github.com/Neilpang/acme.sh#3-install-the-issued-cert-to-apachenginx-etc

值得注意的是, 这里指定的所有参数都会被自动记录下来, 并在将来证书自动更新以后, 被再次自动调用.


# 4. 更新证书

目前证书在 60 天以后会自动更新, 你无需任何操作. 今后有可能会缩短这个时间, 不过都是自动的, 你不用关心.




# 5. 更新 acme.sh

目前由于 acme 协议和 letsencrypt CA 都在频繁的更新, 因此 acme.sh 也经常更新以保持同步. 

升级 acme.sh 到最新版 :
```
acme.sh --upgrade
```

如果你不想手动升级, 可以开启自动升级:

```
acme.sh  --upgrade  --auto-upgrade
```
之后, acme.sh 就会自动保持更新了.

你也可以随时关闭自动更新:

```
acme.sh --upgrade  --auto-upgrade  0
```


# 6. 出错怎么办：
如果出错, 请添加 debug log：

```
acme.sh  --issue  .....  --debug 
```
或者：
```
acme.sh  --issue  .....  --debug  2
```

请参考： https://github.com/Neilpang/acme.sh/wiki/How-to-debug-acme.sh



最后, 本文并非完全的使用说明, 还有很多高级的功能, 更高级的用法请参看其他 wiki 页面.

https://github.com/Neilpang/acme.sh/wiki