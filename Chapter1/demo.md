# 样例

此处展示一个基本的样例，在Vue如何使用该组件，前提是已经安装好了该组件


首先我们定义一个空的Div作为容器
```
<template>
  <div class="hello">
    <div id="container">
    </div>
  </div>
</template>
```

之后我们可以直接导入
```
import GridMap from "segredo-gridmap"
```

并且需要用如下的字段
```
  data () {
    return {
      msg: '',
      gc:  null,
      mapinfo: [],
      image: new Image(),
      showGrid: false
    }
  },
```

我们可以用init初始化容器

```
    let el = document.getElementById("container")
    this.gc = GridMap.init(el)

```


我们伪造一些地图数据，在后面会有详细的说明（包括后面一些操作）
```
    for(var i=0;i < 10; i++){
      let str = i * 100
      this.mapinfo.push({
        "position": str + "," + str,
        "size": "40, 40",
        "collision": true
      })
    }
    this.gc.addMap(this.mapinfo)
    this.image.src = "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1592501604988&di=a2f6970585c0f30af469adb7e4834f4a&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fforum%2Fw%3D580%2Fsign%3D51636e0b7bcf3bc7e800cde4e101babd%2F8682db22720e0cf3e1a0dcfd0146f21fbf09aab5.jpg"
    this.gc.addItems([{
      "position": "200, 300",
      "size": "50, 50",
      "image": this.image,
      "id": 'character'
    }])
```

给摄像机设定追随的物体，并且刷新视图，使用refresh之后图就会被加载出来
```
    this.gc.Camera.setFocus("character")
    this.gc.refresh()
```

可以给我们的键盘上下左右键加上点位移的事件
```
    document.onkeydown = (ev)=>{
      var ev = ev || window.event;
      switch(ev.keyCode){
        case 37:
          this.gc.Ext.moveItem("character", 10, 0, true)
          break;
        case 38:
          this.gc.Ext.moveItem("character", 0, 10, true)
          break;
        case 39:
          this.gc.Ext.moveItem("character", -10, 0, true)
          break;
        case 40:
          this.gc.Ext.moveItem("character", 0, -10, true)
          break;
        case 13:
          if(this.showGrid){
            console.log(this.gc)
            this.gc.hiddenGrid()
            this.showGrid = false
          } else {
            this.gc.showGrid()
            this.showGrid = true
          }
        this.gc.refresh()
      }
    }
```

完整的样例在github上有一个用html写的一样的例子