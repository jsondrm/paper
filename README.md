#### gameStoreDetector项目部署为windows服务，并设置为开机自启
* maven打包生成可执行jar文件
1. 进入项目目录下运行：mvn clean package

     ![Alt text](./生成jar包.png)

* 下载winsw，github下载链接：[https://github.com/kohsuke/winsw/releases](https://github.com/kohsuke/winsw/releases)
(winsw可以将任何应用程序注册成服务)
1. 将GitHub下载的WinSW.NET4.exe和sample-minimal.xml以及.jar放在同一文件夹
&nbsp;
2. 将.exe和.xml文件重命名为项目名+Service，重命名之后为gameStoreDetectorService.exe和gameStoreDetectorService.xml
3. 编辑gameStoreDetectorService.xml文件
4. 安装服务：打开命令提示符界面，进入gameStoreDetectorService.exe所在文件夹，执行命令：gameStoreDetectorService.exe install
5. 启动服务：打开命令提示符界面，执行命令：net start gameStoreDetectorService
6. 运行->输入services.msc，查看服务gameStoreDetectorService
7. 测试：重启电脑服务自动启动
8. 删除服务：
       * 停止服务，执行命令：net stop gameStoreDetectorService
       * 删除服务，进入gameStoreDetectorService.exe所在文件夹，执行命令：gameStoreDetectorService.exe install
9. 服务的相关日志文件在同级目录，可进行查看