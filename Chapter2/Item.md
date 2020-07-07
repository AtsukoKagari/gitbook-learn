# Item

Item其实与Map基本上是一个东西，但是为了方便管理而区分开来了，唯一的区别是如果有碰撞检测的话，Item默认是有碰撞体的。

> Item信息：

与Map信息一样，我们也是用一个数组定义，但是唯一的区别的是建议有一个唯一ID，好方便自身操作，不加ID系统会自动给一个ID，并且给予警告。

```
[
    {
        id: "001"
        position: "200,300",
        size: "100,100"
    },
    {
        id: "002"
        position: "500,400",
        size: "100,100"
    }
]
```

当然我们可以直接调用到该实例
```
gc.Item
```

该实例有如下方法

> addItemInfo：与gridController的方法相同

> removeItem：与gridController的方法相同

> getItem(id)：获得单个Item元素信息

> getItemsInfo()：获得所有Item元素信息