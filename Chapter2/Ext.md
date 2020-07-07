# Ext

该组件是拓展插件，除了基本的地图操作都会放在这里实现，目前实现的内容并不多。

我们也可以直接调用到Ext实例

` gc.Ext `

方法列表：

> gc.Ext.moveItem(id, x, y, relative)

该方法代表把Item id的物体移动到x, y位置上，relative可以表示你的坐标是绝对还是相对的。如果为true表示他是从item.x + x，否则就是直接到x,y位置上。