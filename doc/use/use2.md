# 使用中出现的问题
- (1)为什么显示“warning: adding embedded git repository: how-git”？
    很简单，没有进入到how-git文件夹就开始调用git。
- (2)npm run xxx的时候报错
    首先可能是没有按照babel-loader 8.x对应babel-core 7.x而babel-loader 7.x对应babel-core 6.x的规则来安装，这些npm i --save-dev babel-loader@7.X.X
    其次是初始化npm或者webpack有问题，直接重新初始化或者安装即可。