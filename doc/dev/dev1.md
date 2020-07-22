# 开发步骤详解
- 注（待完善）：
- 1.license只是一个协议，不需要修改。
- 2.开发环境搭建：
    （1）初始化npm即npm init （按版本规范，版本设置为0.0.1、设置目录规范）生成package.json文件:
        package name: (how-git)
        version: (1.0.0) 0.0.1
        description: 短小精悍的git项目实操示例
        entry point: (index.js) src/index.js   // 入口文件
        test command:
        git repository: (https://github.com/Sheng14/how-git)
        keywords: cache
        author: https://github.com/Sheng14
        license: (ISC) MIT
    （2）创建对应文件：
        src： 源代码
        release： 发布结果
        test： 单元测试用例
        doc： 文档
        example： 示例
    （3）安装构建工具（webpack）
    npm i babel-core babel-loader babel-polyfill babel-preset-es2015 babel-preset-latest webpack webpack-cli --save-dev
    （4）创建.babelrc文件(带.都是隐藏文件)和webpack.config.js文件。
    （5）在package.json的scripts里面添加一个命令即"release": "webpack"然后运行release即可打包！只不过可能会报错，注意这是babel-loader和babel-core版本不对应所产生的，babel-loader 8.x对应babel-core 7.x而babel-loader 7.x对应babel-core 6.x，重新安装一个7版本的loder即可！（因为我们的core是6...）打包后的结果可以在bundle.js看到。
    （6）建一个测试的代码，导入我们打包后的内容看看是否显示。
- 3.提交代码
    （1）index.js中有具体代码的实现，example中是对代码进行简单的测试,写完就可以release发布并且检查一下。
    （2）重视文档和测试用例。
    （3）创建文档需要先全局安装npm i gitbook-cli -g，然后创建一个SUMMARY.md来做全局文档的规划，最后gitbook init即可创建对应的文件,里面对应的文档书写完成即可以调用gitbook build 把我们的md文件都变成html格式（这个会创建book文件夹）。而_book是不需要提交的，加到gitignore,每次完成文档修改都build一下就行！
    （4）提交第一版代码，直接先push提交上去再说，然后我们创建tag就能在release中找到了( git tag -a 'v0.0.1' -m "第一版本"   git push origin v0.0.1)，然后放到下载地址中。
    （5）提交完代码后我们需要提交到npm上去，这里要注意名字不能重合，事先搜一下会比较好。(注意npm登录的时候密码是隐藏的，直接假装看得见输入即可)
    （6）安排cdn，好处是自动找到最新版本无需手动修改，需要符合一定规范（前面固定写法，包名和具体哪个文件看自己实际的代码结构）
    （7）升级版本：拉一个新分支(git checkout -b dev)；修改index.js的代码（加一个函数）；修改版本号；修改代码文档测试用例；提交到github(git push origin dev)；再次确认版本号然后合并提交(git merge dev git push origin master)；创建tag提交(git tag -a v0.0.2 -m "v0.0.2" git push origin v0.0.2)；发布到npm。
- 4.创建官网
    （1）利用github pages创建官网，首先创建一个账号.github.io的项目（名字必须如此！）
    （2）下载到本地，建一个html随便写点东西提交到远程。
    （3）然后直接访问账号.github.io直接就能拿到这个页面！（也就是它给我们起了一个静态服务！）
    （4）我们把_book的所有内容拷贝到io那个文件夹里面然后提交到远程即可！
- 5.如何宣传
    （1）围绕相关开源产品的技术干货博客，适当的介绍自己的开源产品。
    （2）把github作为唯一的呃博客主页，然后利用这个往各个博客网站贴，同时注明地址！
    （3）积极回答问题如:segmentfault.com社区、stackoverflow等等，注意回答的技巧。
    （4）做有特色，及时回复用户，方便口碑宣传。
- 6.持续迭代
    （1）统一问题收集区
    （2）定期回复和升级