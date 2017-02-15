
# 转码结果输出到标准输出
$ babel example.js

# 转码结果写入一个文件
# --out-file 或 -o 参数指定输出文件
$ babel example.js --out-file compiled.js
# 或者
$ babel example.js -o compiled.js

# 整个目录转码
# --out-dir 或 -d 参数指定输出目录
$ babel src --out-dir lib
# 或者
$ babel src -d lib

# -s 参数生成source map文件
$ babel src -d lib -s

# babel 的组件安装
## 转码器 babel-preset-es2015
## 命令行转码： babel-cli
## node工具： babel-node
## 自动转码工具： babel-register实时转码，所以在开发环境中使用比较适合
    使用前需要预先加载：
    ·
    require("babel-register");
    require("./index.js");
    ·
##  babel-core 利用Babel的API进行转码
##  babel-polyfill
    Babel默认只转换新的JavaScript句法（syntax），而不转换新的API，比如Iterator、Generator、Set、Maps、Proxy、Reflect、Symbol、Promise等全局对象，以及一些定义在全局对象上的方法（比如Object.assign）都不会转码。

    举例来说，ES6在Array对象上新增了Array.from方法。Babel就不会转码这个方法。如果想让这个方法运行，必须使用babel-polyfill，为当前环境提供一个垫片。

    安装命令如下。

    $ npm install --save babel-polyfill
    然后，在脚本头部，加入如下一行代码。

    import 'babel-polyfill';
    // 或者
    require('babel-polyfill');
    Babel默认不转码的API非常多，详细清单可以查看babel-plugin-transform-runtime模块的definitions.js文件。
    


