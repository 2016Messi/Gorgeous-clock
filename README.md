# Gorgeous-clock
通过使用canvas实现绚丽的时钟效果
项目预览地址： https://2016messi.github.io/Gorgeous-clock/

## 页面结构部分
```
<body>
    <canvas id="canvas"></canvas>
    <script src="js/digit.js"></script>
    <script src="js/Gorgeous-clock.js"></script>
</body>
```
## JavaScript程序主要分为两部分
### digit.js 预先存储一个多维数组
每个内部数组保存内容为 0 或 1 ，通过 1 形成阿拉伯数字 1~9
```
        [
            [0,0,1,1,1,0,0],
            [0,1,1,0,1,1,0],
            [1,1,0,0,0,1,1],
            [1,1,0,0,0,1,1],
            [1,1,0,0,0,1,1],
            [1,1,0,0,0,1,1],
            [1,1,0,0,0,1,1],
            [1,1,0,0,0,1,1],
            [0,1,1,0,1,1,0],
            [0,0,1,1,1,0,0]
        ],//0
        
                [
            [0,0,0,1,1,0,0],
            [0,1,1,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [0,0,0,1,1,0,0],
            [1,1,1,1,1,1,1]
        ],//1
```

### Gorgeous-clock.js相当于主程序部分

```
window.onload=function(){

    var canvas=document.getElementById("canvas");
    var context=canvas.getContext("2d");
    canvas.width=WINDOW_WIDTH;
    canvas.height=WINDOW_HEIGHT;

    curShowTimeSeconds = getCurrentShowTimeSeconds();

    setInterval(function(){
        render(context);
        update();
    },50);
};
```
