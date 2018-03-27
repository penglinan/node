## webpack
### babel

    npm install babel-cli -g
	//-g表示全局化安装

    npm install babel-cli --save-dev
	//本地安装，路径是当前路径

本地安装的同时会在package.json,添加：
```
  "devDependencies": {
    "babel-cli": "^6.26.0"
//    所安装的包：版本号
  }
```
babel预制工具
新建文件.babelrc,内容如下：

    {
       "presets": ["es2015"],
       "plugins" : []
    }
执行命令

    npm install --save-dev babel-preset-es2015 -g
	//在全局安装一次
然后再本地安装一次

	npm install --save-dev babel-preset-es2015
	//package.json里面的依赖就自动添加了
执行babel es6.js编译es6文件成es5，输出

    var a = 10;
    console.log(a);
如何转存成文件

    babel 原文件 --out-file 新文件名字
    babel es6.js --out-file es5.js
    babel es6.js -o es5.js//简写
把src文件夹里面的文件转存到build文件夹（这个文件夹不存在的话会自动创建）

    babel src --out-dir build
    babel src -d build//简写

监视src文件夹里面同步到build文件夹的文件，如果该文件被修改，就自动同步

    babel --watch src -d build