# H5Note
H5学习笔记

## vertical-align
垂直对齐属性，所有浏览器都支持vertical-align属性。vertical-align属性设置元素的垂直对齐方式。该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度和百分比值。这会使元素降低而不是升高。在单元格中，这个属性会设置单元格框中的单元格内容的对齐方式。
主要的值:

* baseline  默认。元素放置在父元素的基线上。
* sub       垂直对齐文本的下标。
* super     垂直对齐文本的上标
* top       把元素的顶端与行中最高元素的顶端对齐
* text-top  把元素的顶端与父元素字体的顶端对齐
* middle    把此元素放置在父元素的中部。
* bottom    把元素的顶端与行中最低的元素的顶端对齐。
* text-bottom  把元素的底端与父元素字体的底端对齐。

示例:

```css
<!DOCTYPE html>
<html>
    <head>
   <meta charset="UTF-8">
   <title>vertical-align</title>
   <style type="text/css">
    *{padding:0px;margin: 0px;}
   
    .warp1{    
              height:80px;
              width: 100%;
              background-color: #14191e;              
              
              line-height: 80px;
              text-align: center;
             }

     .warp1 h1{ color:#fff;
                font-size: 24px;
       }

     .warp2{
              height:400px;
              width: 100%;
              border:1px  #14191e solid;
              /*在此补充代码*/  
              display: table;
             }

     .content{    
              /*在此补充代码*/
              display: table-cell;
              vertical-align: middle;  
              /*text-align: center;*/
              
              }

     .content  p{ width:500px;
                  font-family: "微软雅黑";
                  margin:0 auto;
                  line-height: 1.5em;
                  font-size: 14px;
        }   

   </style>
</head>
<body>
<div class="warp1">
          <h1>欢迎来到慕课网</h1>      
</div>

<div class="warp2">
    <div class="content">
           <p>慕课网，只学有用的！</p>
           <p>
               慕课网（IMOOC）是IT技能学习平台。慕课网(IMOOC)提供了丰富的移动端开发、php开发、web前端、android开发以及html5等视频教程资源公开课。并且富有交互性及趣味性，你还可以和朋友一起编程。
           </p>
    </div>
</div>    

</body>
</html>
```

## padding-top

