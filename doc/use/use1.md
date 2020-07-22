# 使用步骤详解

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
    （3）创建文档需要先全局安装npm i gitbook-cli -g，然后创建一个SUMMARY.md来做全局文档的规划，最后gitbook init即可创建对应的文件,里面对应的文档书写完成即可以调用gitbook build 把我们的md文件都变成html格式（这个会创建book文件夹）。而_book是不需要提交的，加到gitignore。