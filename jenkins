公司内部无法访问jenkins公网地址下载插件，做如下配置
### 配置hosts
修改linux中的/etc/hosts文件，增加如下配置
```
10.93.135.120 rnd-mirrors.huawei.com
10.93.75.202 updates.jenkins-ci.org
```

### 修改系统配置
进入Jenkins的系统管理-》管理插件-》高级页面，把原生URL改成下面的
```
http://rnd-mirrors.huawei.com/jenkins-updates/update-center.json
```

### 取消所有的代理设置

如果点击立即获取时，页面显示如下错误：
`Signature verification failed in update site 'default'`
则在启动参数中增加如下的参数设置，避免进行签名校验（是否可以增加支持签名校验，没有做实验）
以tomcat为例，在tomcat的catalina.sh启动参数中增加
```
JAVA_OPTS="$JAVA_OPTS -Dhudson.model.DownloadService.noSignatureCheck=true"
```
即可。
