# 部署


## 下载
?>由于原生框架较难上手且作者摆烂已经很久没维护了，所以本文章采用基于原生框架开发的喵喵版本yunzai

首先确保你的电脑下载了nodejs，**且nodejs版本大于14**
>https://nodejs.org/zh-cn/download 下载最新版nodejs

同时确保你下载了git，方便后续下载
>https://git-scm.com/download 下载git

之后前往https://gitee.com/yoimiya-kokomi/Miao-Yunzai 下载框架并安装

不想前往的可以直接用下面的代码clone

```
# 使用 Github 
git clone --depth=1 https://github.com/yoimiya-kokomi/Miao-Yunzai.git
cd Miao-Yunzai 
git clone --depth=1 https://github.com/yoimiya-kokomi/miao-plugin.git ./plugins/miao-plugin/


# 使用Gitee
git clone --depth=1 https://gitee.com/yoimiya-kokomi/Miao-Yunzai.git
cd Miao-Yunzai 
git clone --depth=1 https://gitee.com/yoimiya-kokomi/miao-plugin.git ./plugins/miao-plugin/
```

!>务必要全部clone下来,比如gitee的那两行clone命令就要全部执行不然跑不了

## 安装
安装pnpm,安装过的可以直接跳过
```
# 使用npmjs.org安装
npm install pnpm -g

# 指定国内源npmmirror.com安装
npm --registry=https://registry.npmmirror.com install pnpm -g
```

**安装依赖**
```
# 直接安装
pnpm install -P

# 如依赖安装缓慢或失败，可尝试更换国内npm源后再执行install命令
pnpm config set registry https://registry.npmmirror.com
pnpm install -P
```

## 安装redis
yunzai启动还需要redis数据库，因此我们现在去下载redis

?>由于原生redis不支持windows端，所以本文选择使用其他人构建的windows版本进行构建，如果你的系统是linux或者macos也或者说愿意折腾WSL的话可以自行尝试，本文不再赘述

1. 前往https://github.com/tporadowski/redis/releases/tag/v5.0.14.1 下载安装镜像，进行安装
2. 前往你的安装目录，打开**redis-server.exe**这个程序启动redis
3. 返回你的机器人目录，运行“node app"进行初步配置和启动

!>如果双击之后闪退有两种原因
第一种是安装完成后redis会自行启动，所以实际上已经打开了，只需要把服务改成手动并重新启动即可[^1]
如果不是上述情况解决方法看下面

!>请先打开文件扩展名！！！！！！！！！！！！！

然后在 Redis 目录下建一个名称是 start.txt 文本，在新建的 start.txt 文件中加入下面一句话
```
redis-server.exe redis.windows.conf
```
接着将文件名start.txt格式改成start.bat就行了

双击打开 start.bat 就可以了[^2]

>详细解决方法见：https://blog.csdn.net/qq_54431167/article/details/116327191

>第二种方法原文地址：https://jingyan.baidu.com/article/22a299b53ff3b7df18376a1f.html
