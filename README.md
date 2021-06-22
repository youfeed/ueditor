
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

2. 自定义一个 ifame类型的扩展 插入 鼠标放上去 具有 修改和删除

[![ReNsUI.png](https://z3.ax1x.com/2021/06/22/ReNsUI.png)](https://imgtu.com/i/ReNsUI)

html 文件 我放在 `_examples/ifame_hello.html` 把他复制到 编译目录就能调试了 `dist/utf8-php` 

子ifame 通过调用父窗口编辑器 注册事件 等等 


### 1.6 dev-1.5.0 版本二次开发自定义插件注意事项

dev-1.5.0版对于插件的加载逻辑进行了调整，但官网对应的[二次开发功能文档](http://fex.baidu.com/ueditor/#dev-developer)未对相应调整做出开发细节说明，现补充如下：

除进行原有配置外，还需在实例化ueditor编辑器时在 toolbars 参数数组中，加入自定义插件的 uiname，并且注意uiname必须小写，方可正确加载自定义插件。 
