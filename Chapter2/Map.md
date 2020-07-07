# Map

Map代表地图本身的，主要是用于记录地图信息。地图数据有着一个特定的格式，符合该格式才可以被grid正确的识别

> Map信息：

map信息主要遵从着如下的json格式，本质上就是一个数组,这里提供2个Map的基本参数，position为该物体左上角的x,y坐标，size为宽高。

```
[
    {
        position: "200,300",
        size: "100,100"
    },
    {
        position: "500,400",
        size: "100,100"
    }
]
```

当然我们可以直接调用到该实例
```
gc.Map
```

该实例有如下方法

> addMapInfo：与gridController的方法相同

> removeMapInfo：与gridController的方法相同

> removeAll()：清除所有的地图元素

> getMapInfo()：获得所有地图元素信息