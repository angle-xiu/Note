# date名称的问题
+ 名称命名时应该以下划线连接，不能以`-`连接，不然引用的时候会失效。
+ 正确如下
```
var icons = {
    "secret_icon":util.showSrc('workOrder/orderIndex/secret.png'),
    "add_icon":util.showSrc('workOrder/orderIndex/add.png'),
    "search_icon":util.showSrc('workOrder/orderIndex/search_icon.png'),
    "hover_icon":util.showSrc('workOrder/orderIndex/hover2.png'),
}
Page({

    /**
     * 页面的初始数据
     */
    data: {
        ...icons,

    },
    })
```