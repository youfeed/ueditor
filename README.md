
## 1 入门部署和体验

### 1.1 下载编辑器

1. `git clone ` 仓库
2. `npm install` 安装依赖（如果没有安装 grunt , 请先在全局安装 grunt）
3. 在终端执行 `grunt default` 即可编译
4. `cd dist/utf8-php`目录 执行 `http-server` (先安装http服务`npm install --global http-server` 全局) 
5. 访问 ` http://127.0.0.1:8080` 即可本地预览

### 1.2 为了保证代码简洁 html文件为`/_examples/completeDemo.html`
修改HTML后 或者调整完js代码后 执行`grunt default` 会编译到 `dist`下的,浏览器刷新即可

### 1.3 二次需要开发的二点
1. 删除 清除样式 前后空行 复制样式 颜色修改

[![样式中心](https://z3.ax1x.com/2021/06/22/Reto9K.png)](https://imgtu.com/i/Reto9K)

2. 自定义一个 ifame 插入 鼠标放上去 具有 修改和删除

[![ReNsUI.png](https://z3.ax1x.com/2021/06/22/ReNsUI.png)](https://imgtu.com/i/ReNsUI)

子ifame调用父窗口 事件 

### 2.1 传入自定义的参数

编辑器有很多可自定义的参数项，在实例化的时候可以传入给编辑器：
```javascript
var ue = UE.getEditor('container', {
    autoHeight: false
});
```

配置项也可以通过ueditor.config.js文件修改，具体的配置方法请看[前端配置项说明](http://fex.baidu.com/ueditor/#start-config1.4 前端配置项说明.md)

### 2.2 设置和读取编辑器的内容

通getContent和setContent方法可以设置和读取编辑器的内容
```javascript
var ue = UE.getEditor();
//对编辑器的操作最好在编辑器ready之后再做
ue.ready(function(){
    //设置编辑器的内容
    ue.setContent('hello');
    //获取html内容，返回: <p>hello</p>
    var html = ue.getContent();
    //获取纯文本内容，返回: hello
    var txt = ue.getContentTxt();
});
```

ueditor的更多API请看[API 文档](http://ueditor.baidu.com/doc "ueditor API 文档")

### 1.6 dev-1.5.0 版本二次开发自定义插件注意事项

dev-1.5.0版对于插件的加载逻辑进行了调整，但官网对应的[二次开发功能文档](http://fex.baidu.com/ueditor/#dev-developer)未对相应调整做出开发细节说明，现补充如下：

除进行原有配置外，还需在实例化ueditor编辑器时在 toolbars 参数数组中，加入自定义插件的 uiname，并且注意uiname必须小写，方可正确加载自定义插件。 
