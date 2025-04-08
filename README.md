# windows中构建Agent-tars



### 一、环境配置

1.下载安装node.js（v22.14.0-x64）

https://nodejs.org/dist/v22.14.0/node-v22.14.0-x64.msi

2.下载Agent-tars源码：

```
git clone https://github.com/bytedance/ui-tars-desktop.git 

cd ui-tars-desktop
```

3.使用powershell下载最新版PNPM包

```
Invoke-WebRequest https://get.pnpm.io/install.ps1 -UseBasicParsing

Invoke-Expression pnpm self-update
```

4.设置内存大于8g，我这里设置的16g，如果在虚拟机里记得调整虚拟机分配的内存

```
$env:NODE_OPTIONS="--max-old-space-size=16384"
```

### 二、构建与使用项目

1.构建

```
pnpm install
```

2.启动项目

```
pnpm run dev:agent-tars
```

3.使用注意

- AI Models使用默认的Model，禁止勾选Use custom model name，所以最好使用官方的api接口，否则会出现ai调用不了工具的情况

  ![image-20250408150134764](C:\Users\ios\AppData\Roaming\Typora\typora-user-images\image-20250408150134764.png)

- 配置File System，此处删除所有Directory，否则出现无法写入文件，无法读取文件问题，删除后默认写入文件到C:\Users\xxx\\.omega下

![image-20250408150413572](C:\Users\ios\AppData\Roaming\Typora\typora-user-images\image-20250408150413572.png)
