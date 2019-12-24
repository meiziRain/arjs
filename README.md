嘴都气歪了，Typora真他妈垃圾，丢了好几次写的东西了。



## 一些注意点

走的Https，需要服务器，所以要部署到Github Page



基本上参考资料引用aframe-ar.js都是这个连接：https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js，

但是这个需要翻墙，所以要去https://github.com/jeromeetienne/AR.js/blob/master/aframe/build/aframe-ar.min.js下载引用。



微信和chrome 可以打开，但是chrome不知道什么原因，model会很抖。

使用微信测试时需要注意微信的缓存，`debugx5.qq.com`清理缓存。

还可以增加mata元属性，url拼接随机数。

```html
<script type="text/javascript">
  if (window.location.href.indexOf("rid") == -1) {
    window.location =
      "https://meizirain.github.io/birthday_cake/index.html?rid=" +
      Math.random();
  }
</script>
```



比较诡异的是使用https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js时，

```html
<a-entity
  position="-3 0 0"
  rotation="-50 20 -50"
  text="width: 10; value:I am Psyduck. We are pokemon. We love you"
></a-entity>
<a-entity
  position="0 0 0"
  rotation="-140 0 0"
  gltf-model="src: url(res/duck/scene.gltf)"
>
</a-entity>
```

是比较正常的坐标。



而使用https://github.com/jeromeetienne/AR.js/blob/master/aframe/build/aframe-ar.min.js时，

```html
<a-entity         
  position="3 0 0"
  text="width: 10; value:Merry christmas!;"
></a-entity>
<a-entity
  position="0 0 0"
  gltf-model="src: url(res/scene.gltf)"
>
</a-entity>
```

是比较正常的坐标。



坐标概念图：https://www.techbrood.com/aframe/guides?p=building-a-basic-scene#transforming-an-entity-in-3d