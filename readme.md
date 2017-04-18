**说明：**父页面（iframe.html）分为左右结构，右侧部分为iframe（2.html）,iframe中可点击弹出一个模态框，模态框要求显示在父页面。且模态框中包含百度地图的显示。

**问题：**最开始使用直接获取父页面元素创建地图，但存在地图能放大缩小但不能拖拽移动位置的问题。``document.write()``不支持异步。

``var map = new BMap.Map( window.parent.document.getElementById("id") ); ``

**解决方法：**子页面向父页面传参，页面方法直接创建页面地图。

**运行方法：**node.js创建express框架，页面丢进静态文件public，访问localhost:3000/iframe.html即可。