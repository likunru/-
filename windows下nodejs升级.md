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

最近又新看到一个windows系统下，node版本管理工具---nodist
第一步：下载nodist
第二步：下载完成后，可视化安装nodist
第三步：安装nodist,安装完成后就可以使用nodist做版本管理了

下面介绍nodist的使用，在这里只介绍nodist的常用命令，有兴趣进一步了解nodist，可查阅官网（https://github.com/nullivex/nodist）
1. 打印node列表
   $ nodist  
   # 打印当前所有已安装到电脑所有node版本，高亮
   
   $ nodist dist
   #打印所有可下载的node版本
   
2. 切换node版本
   $ nodist global 7.x
   #设置全局的node使用7.x版本
   #这个命令和你直接使用nodist 4.x效果一样

   $ nodist local 7.x
   #设置在当前文件目录下，node使用7.x版本，不影响全局环境变量
   
   $ nodist env 7.x
   #设置当前命令行环境下，node使用7.x版本，不影响全局环境变量
   
3. 切换npm版本
   $ nodist npm global 7.x
   #设置全局的npm使用7.x版本
   
   $ nodist npm global match
   #开启nodist自动匹配模式，总是选择和当前环境node版本相匹配的npm版本
   
   $ nodist npm local 7.x
   #设置在当前文件目录下，npm使用7.x版本，不影响全局环境变量
   
   $ nodist npm env 7.x
   #设置当前命令行环境下，npm使用7.x版本，不影响全局环境变量
   
4. 其他操作
   $ nodist + 7.x
   #先检查7.x版本是否存在，如果不存在则先不安装

   $ nodist + all
   #安装所有模块

   $ nodist - 4.1.1
   #删除node 4.1.1版本   
   
   $ nodist --help
   #显示完整的nodist命令提示