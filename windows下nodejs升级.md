最近在学习react,想用react脚手架create-react-app创建一个react项目。然后下载了create-react-app，打开控制台开始使用create-react-app创建test-react项目，报错提示node版本太低。查了一下使用create-react-app脚手架node版本必须8.*.*版本以上。于是就上网查找了nodejs升级的过程，按照网上的步骤试了好几遍，得到提示都是'bash' 不是内部或外部命令，也不是可运行的程序或批处理文件。

按照网上步骤升级，如下：
第一步：node -v查看nodejs的版本
第二步：npm -v查看npm包管理器的版本
这两步都正常可以继续下面步骤
第三步：升级npm版本  npm install npm -g
第四步：npm -v 发现npm确实升级了
第五步： 安装n模块，npm install -g n --force
第六步： n node版本号/n latest 最新版本/n stable最新的稳定版本
执行第六步就报了上面提到的错误，在网上找了原因，发现windows上不支持n模块。

最后的方法是：
第一步：打开cmd查看之前的node版本安装的路径： where node
第二步：直接去官网下载你想要的版本，安装在上述路径中覆盖即可。
第三步： node -v 发现node版本更新到你想要的版本。