#快速入门
[`zoo`](https://github.com/xwenliang/fis-zoo)是基于[`FIS`](https://github.com/fex-team/fis)的前端模块化解决方案，根据自己团队的需求，优化改造了一些功能。`zoo`命令通过项目根目录下的`fis-config.js`，所以命令参数可以参考**[`F.I.S官方文档`](http://fex.baidu.com/fis-site/docs/beginning/getting-started.html)**。


####工具安装
`zoo`使用`Node.js`开发，以`npm`包的形式发布。因此使用前需要先安装`[Node.js](http://nodejs.cn/)`，再通过`npm`安装命令进行安装。

>npm install fis-zoo -g //安装
>zoo -v                //查看已安装成功的`zoo`版本号

安装遇到困难？[点击这里](https://github.com/fex-team/fis/issues/65)

####下载示例
以此示例项目介绍zoo的基本功能。

>git clone https://github.com/beefe/edu.git
>cd edu/zoo-example/todomvc/

####功能一：本地预览
命令启动本地调试服务器功能，对示例项目进行预览调试。

>zoo server start

####功能二：资源压缩【--optimize(压缩)】
这是前端项目优化中非常重要的一环，提高性能，可以简写为:

>zoo release -o

zoo将项目release到默认的产出目录，可以通过`zoo server open`打开。

####功能三：添加文件版本【--md5戳】
md5其实是内容摘要算法中的一种，根据文件内容自动生成文件版本，并自动更新资源引用路径，来解决缓存更新问题。`zoo release --md5`可以简写为

>zoo release -m

####功能四：资源合并【--pack(打包)】
此命令参数需要上文提到的`fis-config.js`配置文件配合,将对应数组内每个路径的文件打包到pkg/common.js/less。

```javascript
    pack: {
        'pkg/common.js': [
            'js/mod.js',
            'modules/**.js'
        ],
        'pkg/common.less': [
            'css/common.less',
            'modules/**.less'
        ]
    }
```

#So Why?
- [大公司里怎样开发和部署前端代码？](https://www.zhihu.com/question/20790576/answer/32602154)
- [fouber/blog](https://github.com/fouber/blog)