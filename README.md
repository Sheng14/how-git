# how-git
短小精悍的git项目实操示例

## 简介
特色：适合新手，简单易懂，快速上手github项目开发。

## 安装下载
查看文档，亦可clone到本地实现

## 快速使用
简单接入的文档
- 使用文档
- 二次开发文档

## 交流&&提问
https://github.com/Sheng14/How-Git/issues

## 关于作者
github： https://github.com/Sheng14
csdn： https://blog.csdn.net/ODST_TheSolverO5
注（待完善）：
1.license只是一个协议，不需要修改。
2.开发环境搭建：
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