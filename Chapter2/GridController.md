# GridController

GridController是绘图控制器，顾名思义，是控制一切单元组件的起点，我们可以通过初始化获得该组件。

```
var map = document.getElementById("your div name") 
var gc = GridMap.init(map) // 需要传入一个div元素

```

实际上init方法还有一个选填参数Option，传入的是一个字典，字典的内容可以参照Config。


有了该组件之后，我们就可以调用一系列相关组件，当然，gridController也给予了我们一系列简易的操作。


> addMap(mapinfo):添加地图信息

addMap用于添加地图信息，mapinfo详见map。

> removeMap(id):删除地图信息

removeMap用于删除地图信息，前提是你给地图元素标识了ID

> addItems(itemsInfo):添加物品信息

addItems用于添加物品信息，itemsInfo详见item

> removeItem(id):删除物品信息    

removeItem用于删除物品信息，只需要提供ID即可删除

> refresh():刷新地图

> showGrid(size):展示网格

展示网格可以填入网格大小，这样的话会按size绘制网格，否则会使用默认值

> hiddenGrid():隐藏网格