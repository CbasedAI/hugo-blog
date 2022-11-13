---
title: "HTML5 Canvas学习笔记"
date: 2016-09-02T23:59:59+08:00
draft: false
description: ""
tags: ["前端","HTML5"]
categories: ["编程"]

resources:
- name: ""
  src: ""

lightgallery: true


---

## 1.使用canvas元素

在HTML页面上定义`<canvas...>`元素与定义其他普通元素并无任何不同，它除了可以指定`id`、`style`、`class`、`hidden`等通用属性之外，还可以指定如下两个属性：

- `height`：该属性设置该画布组件高度
- `width`：该属性设置该画布组件宽度

在HTML网页上定义`<canvas.../>`元素，它只是一张“空白”的画布。为了在`<canvas.../>`元素上绘图，必须经过如下3步：

1. 获取`<canvas.../>`元素对应的DOM对象，这是一个`Canvas`对象
2. 调用Canvas对象的`getContent()`方法，该方法返回一个`CanvasRenderingContext2D`对象，该对象即可绘制图形。
3. 调用`CanvasRendingContext2D`对象的方法绘图。


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>canvas</title>
</head>
<body>
    <h2>画图入门</h2>
    <canvas id="mc" width="300" height="180" style="border: 1px solid black"></canvas>
    <script type="text/javascript">
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        // 设置填充颜色
        ctx.fillStyle = '#f00';
        // 绘制矩形
        ctx.fillRect(30,40,80,100);
    </script>
</body>
</html>
```


![clipboard.png](/img/bVCFHD)


## 2.绘制几何图形

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>rect</title>
    <h2>绘制图形</h2>
    <canvas id ="mc" width="400" height="280" style="boreder:1px solid black"></canvas>
    <script type="text/javascript">
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        // 设置填充颜色
        ctx.fillStyle = '#f00';
        // 填充一个矩形
        ctx.fillRect(30,20,120,60);
        // 设置填充颜色
        ctx.fillStyle = '#ff0';
        // 填充一个矩形
        ctx.fillRect(80,60,120,60);
        // 设置线条颜色
        ctx.strokeStyle = "#00f";
        // 设置线条宽度
        ctx.lineWidth = 10;
        // 绘制一个矩形边框
        ctx.strokeRect(30,130,120,60);
        // 设置线条颜色
        ctx.strokeStyle = '#0ff';
        // 设置线条宽度
        ctx.lineJoin = 'round';
        // 绘制一个矩形边框
        ctx.strokeRect(80,160,120,60);
        // 设置线条颜色
        ctx.strokeStyle = '#f0f';
        // 设置线条宽度
        ctx.lineJoin = 'bevel';
        // 绘制一个矩形边框
        ctx.strokeRect(130,190,120,60);
    </script>
</head>
<body>

</body>
</html>
```

![clipboard.png](/img/bVCFHK)

## 3.绘制字符串

`CanvasRenderingContext2D`为绘制文字提供了如下两个方法：

- `fillText(String text,float x,float y,[float maxWidth])`：填充字符串
- `stroke(String text,float x,float y,[float maxWidth])`:绘制字符串边框

为了设置绘制字符串时所用的字体、字体对齐方式，`CanvasRenderingContext2D`还提供了如下两个属性：

- `textAlign`：该属性支持`start`、`end`、`left`、`right`、`center`等属性值。
- `textBaseAlign`：设置绘制字符串的垂直对齐方式，该属性支持`top`、`hanging`、`middle`、`alphabetic`、`idecgraphic`、`bottom`等属性值。


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>绘制文字</title>
    <h2>绘制文字</h2>
    <canvas id= "mc" width="600" height="280" style="border: 1px solid black"></canvas>
    <script type= "text/javascript">
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        ctx.fillStyle = '00f';
        ctx.font = 'italic 50px 隶书';
        ctx.textBaseline = 'top';
        // 填充字符串
        ctx.fillText('填充文字',0,0);
        ctx.strokeStyle = '#f0f';
        ctx.font = 'bold 45px 宋体';
        // 绘制字符串的边框
        ctx.strokeText('Canvas绘制文字边框',0,50);
    </script>
</head>
<body>

</body>
</html>
```


![clipboard.png](/img/bVCJ6f)



## 4. 设置阴影

`CanvasRenderingContext2D`为设置图形阴影提供了如下属性：

- `shadowBlur`：设置阴影的模糊度。该属性值是一个浮点数，该数值越大。阴影的模糊程度就越大。
- `shadowColor`：设置阴影的颜色。
- `shadowOffsetX`：设置阴影在X方向的偏移。
- `shadowOffsetY`：设置阴影在Y方向的偏移。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>启用阴影</title>
    <h2>启用阴影</h2>
    <canvas id="mc" width="600" height="280" style="border: 1px solid black"></canvas>
    <script type="text/javascript">
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        // 设置阴影的模糊度
        ctx.shadowBlur = 5.6;
        // 设置阴影的颜色
        ctx.shadowColor = '#222';
        // 设置阴影在X、Y方向的偏移
        ctx.shadowOffsetX = 10;
        ctx.shadowOffsetY = -6;
        ctx.font = 'italic 50px 隶书';
        ctx.textBaseline = 'top';
        // 填充字符串
        ctx.fillText('绘制阴影',0,0);
        ctx.strokeStyle = '#f0f';
        ctx.font = 'bold 45px 宋体';
        // 绘制字符串的边框
        ctx.strokeText('绘制阴影',0,50);
        // 填充一个矩形区域
        ctx.fillRect(20,150,180,80);
        // 绘制一个矩形边框
        ctx.strokeRect(300,150,180,80);
    </script>
</head>
<body>

</body>
</html>
```


![clipboard.png](/img/bVCJ82)


## 5.使用路径

CanvasRenderingContext2D并没有直接提供绘制图形、椭圆等几何图形的方法。为了在Canvas上绘制更复杂的图形，必须在Canvas上启用路径，借助于路径来绘制图形。

在Canvas上使用路径，可按如下步骤进行：

1. 调用`CanvasRenderingContext2D`对象的`beginPath()`方法开始定义路径。
2. 调用`CanvasRenderingContext2D`各种方法添加子路径。
3. 调用`CanvasRenderingContext2D`的`closePath()`方法关闭子路径。
4. 调用`CanvasRenderingContext2D`的`fill()`或`stroke()`方法来填充路径或绘制路径边框。

`CanvasRenderingContext2D`对象提供了如下方法来添加子路径：

- `arc(float x,float y,float radius,float startAngle,endAngle,boolean counterclockwise)`：向Canvas的当前路径上添加一段弧。绘制以x、y为圆心，`radius`为半径，从`startAngle`角度开始，到`endAngle`角度结束的圆弧。`startAngle`、`endAngle`以弧度为单位。**该方法的前两个参数指定圆弧的圆心，第三个参数用于设置圆弧的半径，第四、五个参数则用于设置圆弧的开始角度、结束角度，最后一个角度用于设置是否顺时针旋转。**
- `arcTo(float x1,float y1,float x2,float y2,float radius)`：向Canvas的当前路径上添加一段弧。与前一个方法相比，只是定义弧的方式不同。**该方法也是绘制一段圆弧，确定这段圆弧的方式是：假设从当前点到 *P<sub>1</sub>*(x<sub>1</sub>,y<sub>1</sub>)绘制一条线条，再从*P<sub>1</sub>*(x<sub>1</sub>,y<sub>1</sub>)到*P<sub>2</sub>*(x<sub>2</sub>,y<sub>2</sub>) 绘制一条线条，`arcTo()`则绘制一段同时与上面两条线条相切，且半径为`radius`的圆弧。**
- `bezierCurveTo(float cpX1,float cpY1,float cpX2,float cpY2,float x,float y)`:向Canvas的当前路径上添加一段贝济埃曲线。
- `lineTo(float x,float y)`:把Canvas的当前路径从当前结束点连接到x、y对应的点。
- `moveTo(float x,float y)`:把Canvas的当前路径的结束点移动到x、y对应的点。
- `quadraticCurveTo(float cpX,float cpY,float x,float y)`:向Canvas添加一段二次曲线。
- `rect(float x,float y,float width,float height)`:向Canvas的当前路径添加一个矩形。


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>绘制圆形</title>
    <h2>绘制圆形</h2>
    <canvas id="mc" width="400" height="280" style="border: 1px solid black"></canvas>
    <script type="text/javascript">
        // 获取canva元素对应的DOM对象
        var canvas = document.getElementById("mc");
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        for(var i = 0;i < 10;i++){
            // 开始定义路径
            ctx.beginPath();
            // 添加一段圆弧
            ctx.arc(i * 25,i * 25,(i + 1) * 8,0, Math.PI * 2 ,true);
            // 关闭路径
            ctx.closePath();
            // 设置填充颜色
            ctx.fillStyle = 'rgba(255,0,255,'+(10-i)*0.1+')';
            // 填充当前路径
            ctx.fill();
        }

    </script>
</head>
<body>

</body>
</html>
```

![clipboard.png](/img/bVCKaO)

        
    
使用`arcTo()`方法绘制一个圆角矩形。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>arcTo示例</title>
    <h2> arcTo 示意</h2>
    <canvas id = 'mc' width = '400' height="280" style="border: 1px solid black"></canvas>
    <script type="text/javascript">
        /*
            该方法负责绘制圆角矩形
            x1、y1:圆角矩形左上角的坐标
            width、height:控制圆角矩形的宽、高
            radius:控制圆角矩形的四个圆角的半径
         */
        function createRoundRect(ctx, x1, y1, width, height, radius)
        {
            // 移动到左上角
            ctx.moveTo(x1 + radius,y1);
            // 添加一条连接到右上角的线段
            ctx.lineTo(x1 + width - radius,y1);
            // 添加一段圆弧
            ctx.arcTo(x1 + width, y1, x1 + width, y1 + radius, radius);
            // 添加一条连接到右下角的线段
            ctx.lineTo(x1 + width, y1 + height - radius);
            // 添加一段圆弧
            ctx.arcTo(x1 + width, y1 + height, x1 + width - radius, y1 + height, radius);
            // 添加一条连接到左下角的线段
            ctx.lineTo(x1 + radius, y1 + height);
            // 添加一段圆弧
            ctx.arcTo(x1, y1 + height, x1, y1 + height - radius, radius);
            // 添加一条连接到左上角的线段
            ctx.lineTo(x1,y1 + radius);
            //添加一段圆弧
            ctx.arcTo(x1, y1, x1 + radius, y1, radius);
            ctx.closePath();
        }
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContex2D对象
        var ctx = canvas.getContext('2d');
        ctx.lineWidth = 3;
        createRoundRect(ctx, 30, 30, 200, 100, 20);
        ctx.stroke();
    </script>
</head>
<body>

</body>
</html>
````


![clipboard.png](/img/bVCKgJ)

其中`moveTo(x,y)`和`lineToo(x,y)，前者是把绘制点移动到指定点，而后者则负责绘制从当前点到指定点(x,y)的线条。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>lineTo示例</title>
    <h2>lineTo示例</h2>
    <canvas id = "mc" width = "500" height="380" style="border: 1px solid black;"></canvas>
    <script type="text/javascript">
        /*
            该方法负责绘制多角星
            n: 该参数通常应设为奇数,控制绘制N角星
            dx、dy: 控制N角星的位置
            size: 控制N角星的大小
         */
        function createStar(context, n, dx, dy, size)
        {
            // 开始创建路径
            context.beginPath();
            var dig = Math.PI / n * 4;
            context.moveTo(dx, y + dy);
            for(var i = 0; i < n; i++)
            {
                var x = Math.sin(i * dig);
                var y = Math.cos(i * dig);
                // 绘制从当前点连接到指定点的线条
                context.lineTo(x * size + dx, y * size + dy);
            }
            // 关闭路径
            context.closePath();
        }
        // 获取canvas元素对应的DOM对象
        var canvas = document.getElementById('mc');
        // 获取在canvas上绘图的CanvasRenderingContext2D对象
        var ctx = canvas.getContext('2d');
        // 绘制3角星
        createStar(ctx, 3, 60, 60, 50);
        ctx.fillStyle = '#f00';
        ctx.fill();
        // 绘制5角星
        createStar(ctx, 5, 160, 60, 50);
        ctx.fillStyle = '#0f0';
        ctx.fill();
        // 绘制7角星
        createStar(ctx, 7, 260, 60, 50);
        ctx.fillStyle = '#00f';
        ctx.fill();
        // 绘制9角星
        createStar(ctx, 9, 360, 60, 50);
        ctx.fillStyle = '#f0f';
        ctx.fill();
    </script>
</head>
<body>

</body>
</html>
```


![clipboard.png](/img/bVCKjo)