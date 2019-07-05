# win10 配置nodejs8.0.0环境变量、安装cnpm镜像、安装vue-cli等命令.

1.下载nodejs。

这里用的是8.0.0版本



2.安装，这里本人安装在D:\Program Files\nodejs

安装后，打开shell脚本

node -v		--nodejs版本

npm -v		--npm版本

说明已经安装成功。



3.环境变量配置

1).安装后会在系统变量生成 D:\Program Files\nodejs 的环境变量。这时候，就可以在shell脚本执行npm命令了

2).在NodeJs下新建"node_global"及"node_cache"两个文件夹，打开shell输入

```
npm config set prefix "D:\Program Files\nodejs\node_global"
npm config set cache "D:\Program Files\nodejs\node_cache"
```

右键我的电脑-属性-高级系统设置-环境变量，打开环境变量设置窗口

修改用户变量Path，修改默认的配置为刚才设置的prefix路径



4.安装淘宝镜像

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

如果出现 npm ERR! code EINTEGRITY，执行 npm cache verify，npm cache clean，npm cache clean --force

 安装完执行cnpm -v，出现cnpm无法识别

接下来，配置NODE_PATH	D:\Program Files\nodejs\node_global\node_modules

添加PATH	D:\Program Files\nodejs\node_global

重新打开shell，执行cnpm -v。出现版本说明安装成功



