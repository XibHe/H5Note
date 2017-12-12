# H5Note
H5学习笔记

## vertical-align
垂直对齐属性，所有浏览器都支持vertical-align属性。vertical-align属性设置元素的垂直对齐方式。该属性定义<font color="#DC143C">行内元素</font>的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度和百分比值。这会使元素降低而不是升高。在单元格中，这个属性会设置<font color="#DC143C">单元格</font>框中的单元格内容的对齐方式。
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

```html
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
padding-top 属性设置元素的上内边距（空间）。行内非替换元素上设置的上内边距不会影响行高计算，因此，如果一个元素既有内边距又有背景，从视觉上看可能延伸到其他行，有可能还会与其他内容重叠。不允许指定负内边距值。

<font color="#DC143C">注意</font>：不允许使用负值。

可能的值: 

* length	   规定以具体单位计的固定的上内边距值，比如像素、厘米等。默认值是 0px。
* %	          定义基于父元素宽度的百分比上内边距。此值不会如预期的那样工作于所有的浏览器中。
* inherit	   规定应该从父元素继承上内边距。

示例:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>背景</title>
    <style>
     /*此处写代码*/
      div{width: 500px;
          height: 350px;
          text-align: center;
          background-image: url(http://climg.mukewang.com/58dc9d360001d65806500650.jpg);
          padding-top: 300px;
          font-weight: bold;
          font-size: 22px;
      }
    </style>
</head>
<body>
    <div>
                 《长歌行》
        <br>
        <br>青青园中葵，朝露待日晞。
        <br>阳春布德泽，万物生光辉。
        <br>常恐秋节至，焜黄华叶衰。
        <br>百川东到海，何时复西归。
        <br>少壮不努力，老大徒伤悲。
        <br>
    </div>
</body>
</html>

```

## JSPatch OC转JS

1. OC中的NSDictionary转换，使用**setValue_forKey**

eg. 

```objectivec
NSDictionary *param = @{@"clinicId":clinkId,@"pageNo":[NSString stringWithFormat:@"%ld",self.pageNum],@"pageSize":@"20"};
```
转换为：

```js
var param = NSMutableDictionary.dictionary();
param.setValue_forKey(clinkId, "clinicId");
param.setValue_forKey(NSString.stringWithFormat("%ld", self.pageNum), "pageNo");
param.setValue_forKey("20", "pageSize");
```

2. 读取字典NSDictionary对应的键值

eg.

```objectivec
NSArray *arr = model.body.content[@"list"];
```

转换为：

```js
var arr = model.body().content().valueForKey("list");
```

3. 使用**setValuesForKeysWithDictionary**设置model

eg.

```objectivec
 for (int i = 0; i<arr.count; i++) {
  LZPartnerWalletDetailModel *model = [[LZPartnerWalletDetailModel alloc]init];
  [model setValuesForKeysWithDictionary:arr[i]];
  [self.dataArr addObject:model];
}
```

转换为：

```js
for (var i = 0; i < arr.count(); i++){                                                                                                                                                    var model = LZPartnerWalletDetailModel.alloc().init();                                                                                  var dic = arr.objectAtIndex(i);                                                                 model.setAmount(dic.valueForKey("amount"));                                         model.setContent(dic.valueForKey("content"));                                                                 model.setCreatetime(dic.valueForKey("createtime"));                                                                    model.setStatus(dic.valueForKey("status"));                                                            model.setReason(dic.valueForKey("reason"));                                                                                   self.dataArr().addObject(model);                                                                                                                                                 }
```

其中，dic需要一个个的使用dic.valueForKey来设置。