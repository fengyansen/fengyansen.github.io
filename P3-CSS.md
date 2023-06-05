# 前端-CSS

## HTML内部添加样式(美化文档)

```html
<p style="font-size:14px;color:white"></p>
```

### 字体大小/字体粗细

#### 字体大小

设置格式：font-size:36px（字体的大小 36px-->字体大小的尺寸)

```html
<!-- 设置字体的大小为12px -->
<p style="font-size: 12px;">
  一个轻量级和模块化的前端框架，用于开发快速和强大的web接口。
</p>
<!-- 设置字体的大小为24px -->
<p style="font-size: 24px;">
  一个轻量级和模块化的前端框架，用于开发快速和强大的web接口。
</p>
```

#### 字体加粗

设置格式：font-weight:100（值可以是100，200，300，400，500，600，700，800，900中任何一个，也可以是英文（normal(正常粗细)、lighter（细）、bold（粗）、bolder（更粗）

```html
<p style="font-weight: 200;">优课达--学的比别人好一点～</p>
<p style="font-weight: lighter;">优课达--学的比别人好一点～</p>
<p style="font-weight: 400;">优课达--学的比别人好一点～</p>
<p style="font-weight: normal;">优课达--学的比别人好一点～</p>
<p style="font-weight: 700;">优课达--学的比别人好一点～</p>
<p style="font-weight: bold;">优课达--学的比别人好一点～</p>
```

### 字体颜色、文字对齐方式

#### 字体颜色

##### 英文字母形式：

color：black；color：blue；color：red；

##### 十六进制颜色：

由#开头，后面跟三个数字，每个数字的范围为00-FF。每个数字代表一种颜色，最终的颜色由这三种颜色调和而成

color：#DAEBFC ；  color：#D5E8D4

#### rgb形式

由r（red）、g（green）、b（blue），每种颜色的范围为0-255，值越大颜色越深

color：rgb（253，217，106）

##### rgba形式

相比rgb多了一个a，这个a代表的是透明度，a的值在0-1之间

color：rgba（253，217，106，1.0）

color：rgba（253，217，106，0.3）

注意：

1. 多数情况下建议使用十六进制表达方式

2. 调试的时候可以用英文字母形式，初期的调试就是随便设置一个颜色，查看区块是否存在，区块大小等
3. 如果要设置透明度和背景透明度就要用到rgba形式

```html
<h3 style="color:#ff9a9e;font-weight:700;font-size: 24px;">UIzards</h3>
<h4 style="font-size: 16px;color: #474d5d;font-weight: 400;">
  Senior UX Designer
</h4>
<p style="font-size: 14px;color:#84868d;">
  Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet
  doming id quom placerat facer possim assum. Typi non habent claritatem
  insitam; est usus legentis in iis qui faorum claritatem. Investigationes
  demonstraverunt lectores legere me lius quod ii legunt saepius.
</p>
```

#### 文字对齐方式

文字居中对齐：text-align：center

文字左对齐：text-align：left

文字右对齐：text-align：right

### 文字行高、字间距、字体

#### 行高

设置格式：line-height：30px

```html
<p>
  We understand every aspect of project and we put a great amount of time in
  understanding the project.
</p>

<p style="line-height:32px;">
  We understand every aspect of project and we put a great amount of time in
  understanding the project.
</p>
```

#### 使文字上下居中

_当行高和矩形的高度一样的时候，文字在矩形中上下居中_

```html
<button
  style="width: 120px;height:50px;text-align: center;line-height:50px;color:white;font-size: 18px;"
>
  提交
</button>
```

#### 字间距

1. 英文的字间距是每个字母之间的距离
2. 中文是每个汉字之间的距离

设置格式：letter-spacing：30px

#### 字体

设置格式：font-family：sans-serif（关键字+值）

```html
font-family: 'Goudy Bookletter 1911', sans-serif, 'Gill Sans Extrabold';
```

页面加载后先去寻找Goudy、Bookletter、1911这三种字体，如果都没有安装，则用默认的微软字体

注意：

1. 多个字体之间用英文逗号隔开
2. 字体名称中间由空格的时候，要加引号，单引号和双引号都行："Times News Roman"
3. 中文名称要用引号，单引号和双引号都行："宋体"

## CSS-引入方式（内部样式）

### 内部样式

在head标签里声明一个<style></style>标签，样式全部放在这个标签里

```html
<style>
p {
  font-size: 16px;
  color: #ffffff;
}
</style>
```

### 外部样式

为了避免HTML文件出现头重脚轻的现象（css的代码要比html多），需要实现代码的分离，HTML负责结构，CSS负责样式。

1. 新建一个index.css文件

2. 将HTML代码头部的style标签内的样式全部拷贝过去

3. 将复制的css样式粘贴进index.css文件中

4. 建立HTML和CSS文件的联系，用link标签引入CSS文件

   ```html
   <link rel="stylesheet" href="./index.css">
   ```

### 补充知识点

#### css的内部样式注释

```css
/*css注释内容*/
<style>
/* 写CSS的基础样式 */
.base{
  /* 基础字体大小 */
  font-size: 14px;
  /* 基础字体颜色 */
  color:#000000;
}
</style>
```

#### css的外部样式注释

```css
/* 写CSS的基础样式 */
.base {
  /* 基础字体大小 */
  font-size: 14px;
  /* 基础字体颜色 */
  color: #000000;
}
```

#### link的标签属性

```html
<link rel="stylesheet" type="text/css" href="index.css" />
```

rel：规定了当前文档与被链接文档之间的关系，但是rel的属性的stylesheet值被所有浏览器支持

stylesheet：文档的外部样式表

type：规定了被链接文档的MIME（多用途互联网邮件扩展类型），最常见的值是text/css

href：其后跟要引入的链接地址

### 常用选择器

注意：

1. 添加新的效果
2. 改变之前已经存在的效果

#### 类选择器

作用：在普通中寻找特别（个别属性需要改变）

一个标签上面可以添加多个类名，类名之间要用空格隔开

```html
<p class="article">
  class是定义类的关键字，article是类名，类名可以任意，但是要符合规范
</p>

<p class="common color font-size">
  common设置通用样式，color设置特殊颜色，font-size设置特殊字体大小
</p>
```

类名的先后顺序不影响最终样式

<style></style>标签中的类名影响先后顺序

#### id选择器

```html
<p id="p-item">这是一段文字</p>
```

##### id选择器的使用

```css
/*id选择器的使用*/
#p-item {
  font-size: 24px;
  font-weight: 400;
}
```



##### 使用id选择器



1. id选择器在文档中只会出现一次
2. 一个标签上不可以定义多个id名

### 高级选择器

#### 后代选择器(空格)

```css
/* 选择id名为password的标签内部所有类名为box的元素内部的所有p标签 */
#password .box p{}
/* 选择所有p标签内部的所有span标签 */
p span{}
/* 选择所有p标签内部的所有类名为spanItem的标签 */
p .spanItem{}
```

##### 实例1：

```html
<ul class="first-ul">
    <li>苍苍竹林寺，杳杳钟声晚。</li>
    <li>荷笠带斜阳，青山独归远。</li>
</ul>
<ul class="second-ul">
    <li>白日依山尽，黄河入海流。</li>
    <li>欲穷千里目，更上一层楼。</li>
</ul>
```

```css
ul li {
    /* 去除li标签前面的小圆点 */
    list-style: none;
    font-size: 22px;
}

.first-ul li {
    color: rgb(212, 166, 28);
}

.second-ul li {
    color: rgb(230, 127, 122);
}
```

##### 实例2

```html
<ul>父
    <li>子
        <p>孙
            <span>曾孙
                <a href="">曾曾孙</a>
            </span>
        </p>
    </li>
</ul>
```

选中曾曾孙的方法

```css
/* 方法一： */
a{}
/* 方法二 */
ul a{}
/* 方法三 */
ul li p a{}
/* 方法四 */
ul li p span a{}
```

##### 实例3

```html
<ul>父
    <li>子
        <p class="p-one">孙
            <span>曾孙
                <a href="">曾曾孙1</a>
            </span>
        </p>
        <p class="p-two">孙
            <span>曾孙
                <a href="">曾曾孙2</a>
            </span>
        </p>
    </li>
</ul>
```

**选中曾曾孙1的方法**

```css
/* 方法一 */
ul li .p-one span a{}
/* 方法二 */
.p-one span a{}
```



#### 交集选择器

```html
<ul>
    <li><a href="" class="special">电子产品</a></li>
    <li><a href="">家居服饰</a></li>
    <li><a href="">电竞手办</a></li>
    <li><a href="" class="special">家装服务</a></li>
    <li><a href="">房屋出租</a></li>
</ul>
```

_实现电子产品和家装服务的颜色与其它不同_

```css
ul li {
    list-style: none;
    font-size: 22px;
}

ul li a {
    /* 去除a标签的下划线 */
    text-decoration: none;
    /* 这里的颜色一定要在a标签上设置，因为a标签默认会去设置字体颜色，会层叠掉默认的黑色 */
    color: black;
}

ul li a.special {
    color: orangered;
}
```



#### 子选择器

只会关心其子代，而不关心孙代

```html
<p>
    <span>Span 1. 在p标签内
        <span>Span 2. 在p标签的span标签内</span>
    </span>
</p>
<span>Span 3. 与p标签相邻</span>
```



```css
span {
    color: black;
}

p>span {
    color: orangered;
}
```



#### 并集选择器

给不同的标签或者不同类名的标签添加相同的样式

```css
.box,p,h3,.phone{}
```

### 选择器的优先级

#### 单个选择器的优先级

id选择器>类选择器>标签选择器

#### 文字属性的继承性

### 高级选择器的优先级

#### 权重的计算方法

id选择器的权重为100，类选择器的权重为10，标签选择器的权重为1

```css
.param #item span {
}
```

权重=100+10+1

#### 权重的作用

_决定当用两个不同的选择器给同一个标签设置了相同的属性，该听谁的_

```html
<ul class="ul-item">
  <li>
    <p>文字的颜色到底是什么颜色？</p>
  </li>
</ul>
```

```css
ul li p {
  color: blue;
}
p {
  color: red;
}
```

注意：

1. 层叠性只有在权重一样的情况下才会适用
2. 权重越大，优先级越高
3. 权重的适用范围：选中

## 盒模型

div标签由四部分组成

1. 内容区（content）
2. 内边距（padding）
3. 边框（border）
4. 外边距（margin）

![image-20230524101504097](图片/image-20230524101504097.png)

### 内容区-content

<u>div标签没有高度，宽度默认和父标签的宽度一样</u>

```html
<ul>
  <li>
    <div></div>
  </li>
</ul>
```

画一个矩形，它的宽高对应两个CSS属性：width、height

#### 实例

下面我们来画一个宽200px，高100px的矩形

```html
<div class="box"></div>
```

```css
.box {
  width: 200px;
  height: 100px;
}
```

#### 给矩形添加背景颜色

*设置格式：background：背景颜色*

```html
<div class="box"></div>
```

```css
.box {
  width: 200px;
  height: 100px;
  background-color: purple;
}
```

#### 百分百尺寸

设置块元素的宽高，除了px形式还有%形式，比如：

```html
<div class="father">
  <div class="son"></div>
</div>
```

```css
.father {
  width: 200px;
  height: 80px;
  background-color: #5b6dcd;
}
.son {
  width: 60%;
  height: 20%;
  background-color: #fec03e;
}
```

注意：

这里的%是相对于父元素的，也就是说，子元素的宽度是父元素的60%

### 内边距-padding

#### 实例

```html
<div class="box">
    All afternoon his tractor pulls a flat wagon with bales to the barn, then back to the waiting chopped field. 
    It trails a feather of smoke. Down the block we bend with the season: shoes to polish for a big game,storm windows to batten or patch. 
    And how like a field is the whole sky now that the maples have shed their leaves, too.
</div>
```

```css
.box{
    width:300px;
    height:300px;
    background-color:purple;
    padding:20px;
    color:white;
}
```

![image-20230524104006305](图片/image-20230524104006305.png)

内边距默认都是相同的，如果不同，需要这样写

```css
.box {
    padding-top: 20px; /*上内边距*/
    padding-right: 20px; /*右内边距*/
    padding-bottom: 20px; /*下内边距*/
    padding-left: 20px; /*左内边距*/
}
```

#### 上下左右都一样

```css
div{
    padding:20px 20px 20px 20px;
}
```

#### 上下一样，左右一样

```css
div{
    padding: 20px 30px;
}
```

#### 上下一样，左右不一样

```css
div{
    padding: 20px 30px 20px 10px;
}
```

#### 上下不一样，左右一样

```css
div{
    padding: 30px 10px 20px;
}
```

#### box-sizing

规定了如何计算一个元素的总宽度和高度（它有两个值content-box、border-box，默认是content-box）

##### content-box计算公式

```txt
width = 内容的宽度
height = 内容的高度
```

##### border-box计算公式

```txt
width = border + padding + 内容的宽度
height = border + padding + 内容的高度
```

##### 实例1

```html
<div class="father">
    <div class="son"></div>
</div>
```

```css
.father{
    width:200px;
    height: 100px;
    background-color: #5C70CA; 
}

.son{
    box-sizing: content-box;
    width: 100%;
    height: 40px;
    background-color:#FEC03E;
}
```

##### 实例2

```css
.father{
    width:200px;
    height: 100px;
    background-color: #5C70CA; 
}

.son{
    box-sizing: content-box;
    width: 100%;
    height: 40px;
    /* 添加padding */
    padding: 0px 20px;
    background-color:#FEC03E;
}
```

```css
.father{
    width:200px;
    height: 100px;
    background-color: #5C70CA; 
}

.son{
    /* 修改box-sizing */
    box-sizing: border-box;
    width: 100%;
    height: 40px;
    /* 添加padding */
    padding: 0px 20px;
    background-color:#FEC03E;
}
```

### 盒模型-border（边框）

```css
.box {
  /* 设置矩形大小 */
  width: 200px;  
  height: 30px;
  /* 设置边框线 */
  border-width: 2px;
  border-color: grey;
  border-style: solid;
}
```

width：边框粗细

color：边框颜色

style：边框的线型（solid：实线     dashed：虚线 ）

#### 边框的简写

顺序无所谓

```css
.box {
  border: 2px solid blue;
}
```

#### 分别设置边框

```css
.box {
  /*设置顶部border*/
  border-top-color: blue;
  border-top-style: solid;
  border-top-width: 2px;
  /*那么接下来，left，right，bottom是类似的，这里忽略不写*/
}
```

#### 简写

```css
.box {
  /* 添加顶部border */
  border-top: 1px solid black;
  /*添加右侧border*/
  border-right: 3px solid orange;
  /*添加底部border*/
  border-bottom: 5px dashed pink;
  /*添加左侧border*/
  border-left: 10px dashed purple;
}
```

#### 利用层叠性设置边框

```css
.box {
  /*设置矩形的宽*/
  width: 300px;
  /*设置矩形的高*/
  height: 300px;
  /*设置矩形的背景颜色*/
  background-color: white;
  /*设置矩形的边框*/
  /*统一设置矩形的所有边框样式*/
  border: 2px solid black;
  /*重新设置一个下边框的样式来层叠掉统一设置的边框的样式*/
  border-bottom: 5px solid orange;
}
```

#### 无边框的设置

```css
.box {
  border-bottom: none;
}
```

#### 圆角

矩形的圆角设置

```css
div {
  width: 200px;
  height: 200px;
  border-radius: 18px;
  border: 1px solid black;
}
```

##### 圆角的分开设置

*左上角，右上角，右下角，左下角*

```css
.box {
  width: 200px;
  height: 200px;
  background-color: violet;
  border-top-left-radius: 5px;
  border-top-right-radius: 10px;
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 15px;
}
```

##### 阴影（呈现立体感）

实现原理：可以看作是在矩形下面有一个重叠的，同样大小的矩形，如果它在x轴，y轴上移动，就会有阴影的效果

x偏移量：在x轴上移动，向右为正

y偏移量：在y轴上移动，向下为正

阴影模糊半径：就是边线的清晰度

阴影扩散半径：就是向外伸展

阴影颜色：就是矩形下面那个矩形的背景色

```html
<div class="box"></div>
```

```css
.box {
  width: 200px;
  height: 200px;
  border: 1px solid #c4c4c4;
  /* x偏移量 | y偏移量 | 阴影模糊半径 | 阴影扩散半径 | 阴影颜色 */
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 15px;
}
```

### 综合运用

#### 自己写的

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" type="text/css" href="index.css" />
</head>

<body>
    <div class="box">
        <div class="son">
          首页  
        </div>
       <div class="you">
           优课达学院 
       </div>
      <div class="app">
           App下载 
      </div>
       
    </div>
   
</body>

</html>
```

```css
.box{
  height: 60px;
  font-size: 16px;
  background: #FFFFFF;
  color: #333333;
  text-align: center;
  border: 1px solid #a4a4a4;
  display: inline-block;
}
.box .son{
  box-sizing: border-box;
  height: 60px;
  color: #ffffff;
  background: #0091ff;
  padding: 15px 15px;
  display: inline-block;
}
.box .you{
  box-sizing: border-box;
  height: 60px;
  padding: 15px 15px;
  display: inline-block;
}
.box .app{
  box-sizing: border-box;
  height: 60px;
  padding: 15px 15px;
  display: inline-block;
}
```

#### 答案更简便

运用了无序序列

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <ul>
        <!-- 给第一项添加类名，方便设置它的特殊样式 -->
        <!-- 类名的选取要考虑语义化，current可表示当前选中的这一项，用active或者home之类的也是可以的 -->
        <li class="current">首页</li>
        <li>优课达学院</li>
        <li>App下载</li>
    </ul>
</body>

</html>
```

```css
/* 列表默认样式清除 */
ul {
    list-style: none;
    padding: 0px;
    margin: 0px;
  }
  
  ul {
    /* 因为文本样式具有继承性，所以我们可以把li公共文本样式提到父元素ul中 */
    /* 当然，这些文本样式直接写在li上也是可以的 */
    color: #333333;
    font-size: 16px;
    /* 设置边框 */
    border: 1px solid #a4a4a4;
    /* 将ul从块状元素变为行内块元素，这样做的话，ul的宽度将不再是body宽度的100% */
    /* 它的宽度将是里面li的总宽度，即ul的宽度将由内容宽度决定 */
    display: inline-block;
  }
  
  ul li {
    /* 
          display:inline-block可以让一个块元素和行内元素在同一行显示
          具有想同属性的块元素也可以并排显示
      */
    display: inline-block;
    /* 每个li的宽度不是固定的，是有文字+左右各15px形成的 */
    padding-left: 15px;
    padding-right: 15px;
    /* 给li设置height */
    height: 60px;
    /* 给li设置和height等值的line-height，这样可以使li中的单行文字在垂直方向上居中 */
    line-height: 60px;
  }
  
  /* 利用css的层叠性修改第一项li的样式 */
  /* ul li.current表示选中ul的后代li中类名为current的元素 */
  ul li.current {
    color: #ffffff;
    background-color: #0091ff;
  }
  
```

### 盒模型--margin

矩形与矩形之间的距离

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>案例</title>
    <style>
        div {
            width: 300px;
            height: 100px;
            background-color: #D5E8D4;
            border: 1px solid #82B366;
        }

        .box{
          background-color: #F5F5F5;
          border: 1px solid #FF0818;
          margin-top: 20px;
          margin-bottom: 20px;
        }
    </style>
</head>

<body>
    <div></div>
    <div class="box"></div>
    <div></div>
</body>

</html>
```

#### 简写

```css
.box{
    /*总写*/
    margin: 20px;
    /*分开写*/
    margin-top: 20px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 20px;
}
```

#### 两个盒子之间margin的计算

##### 水平距离

如果盒子没有设置margin-left，默认为0px

##### 垂直距离

谁设置的距离大，垂直距离就是谁

![image-20230525101917514](图片/image-20230525101917514.png)

设置两个盒子之间的距离为50px，只需设置上面盒子的底部为50px即可

##### 盒子左右居中

左右居中的前提是，盒子必须有宽度

```html
<div class="father"> 
    <div class="son"></div>
</div>
```

```css
.father{
    width:400px;
    height:200px;
    border: 1px solid #ccc;
}

.son{
    width:200px;
    height:100px;
    margin:0 auto;
    border: 1px solid #ccc;
}
```

#### 综合运用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <!-- 注意：取类名需要考虑语义化，尽量使用意思贴合的英文，尽量不使用拼音或无意义的单词字母 -->
    <div class="box">
        <img src="https://gw.alicdn.com/bao/uploaded/i1/749716436/O1CN01OSPWqa1xPjeErSSzf_!!749716436-0-pixelsss.jpg">
        <div class="introduce">人本春季红色帆布鞋男网红休闲布鞋潮鞋百搭运动小白鞋子男运动鞋</div>
        <div class="price">¥78.3</div>
    </div>
</body>

</html>
```

```css
/* 
  这个题目中有个容易搞错的点，即“居中”的实现：
  1. 图片的居中
     图片的居中是通过给div.box设置text-align: center;实现的，这是因为图片是行内元素，这个比较好理解。
  2. div.introduce的居中
     div.introduce的居中是通过margin: 0 auto;实现的，因为这是个宽度小于父元素的块状元素，所以要使用margin来让它居中，text-align: center;无法使块状元素本身在父元素里居中。
  3. 价格的居中
     价格的居中也是通过给div.box设置text-align: center;实现的，这个具有一定的迷惑性，其实这是因为div.price继承了div.box的text-align属性，从而使里面的价格文本居中了。
 */

 .box {
    width: 234px;
    border: 1px solid #c4c4c4;
    /* text-align: center; 这一句可以实现图片的居中和价格的居中 */
    /* 因为图片和div.price元素中的文本内容都是行内内容 */
    text-align: center;
    padding: 20px 0px;
  }
  
  img {
    width: 185px;
    height: 185px;
    margin-bottom: 8px;
  }
  
  .introduce {
    width: 135px;
    /* 需要给div.introduce设置高度，否则不存在文本超出这个盒子这个情况根本不会发生 */
    /* 因为盒子的高度在不设置的情况下会随着内容的增加而增加，内容永远不会超出盒子 */
    height: 40px;
    font-size: 14px;
    color: #333;
    line-height: 20px;
    /* 给div.introduce设置width为135px后，可以使用margin: 0 auto;使它在div.box元素中左右居中 */
    margin: 0 auto;
    /* 重新设置margin-bottom可以覆盖上一句margin简写中的margin-bottom的值 */
    margin-bottom: 10px;
    /* 让超出的文本隐藏 */
    overflow: hidden;
  }
  
  .price {
    font-size: 18px;
    color: #ff0036;
    line-height: 18px;
  }
  
```

### 盒模型--display：block/none

#### display：block

独占一行

#### 块元素性质：

1. 块级标签_独占一行_（比如：h标签）
2. 块元素可以设置宽高（设置高和宽，再设置背景颜色，所设置的这种范围内都可以变色），而行内元素不可以（只会在有内容的地方显示背景颜色）

#### 行内元素和块元素之间的转换

块元素默认的display属性的值是block

行内元素默认的display属性的值是inline

转换的过程就是改变了它的display属性

##### 行内元素转块元素

```html
<span class="demo"> 这是一个span标签 </span>
```

```css
.demo {
  /*将span标签转换成块元素*/
  display: block;
  width: 300px;
  height: 100px;
  background-color: #fff2cc;
}
```

##### 块元素转行内元素

```html
<div class="demo">这是一个span标签</div>
```

```css
.demo {
  /*将div标签转换成行内元素*/
  display: inline;
  /* 转换成行内元素以后，宽、高的设置就会失效，即使我们仍然设置了它们 */
  width: 300px;
  height: 100px;
  /* 背景颜色也不会是300*100范围，而是文字有多少面积，背景颜色就又多少面积 */
  background-color: #fff2cc;
}
```

#### display：none

当给标签设置了这个属性值，标签就会消失，在网页布局中最常用的就是用none、block来控制元素的显示与隐藏

```html
<div>盒子1</div>
<div class="box2">盒子2</div>
<div>盒子3</div>
```

```css
div {
  width: 300px;
  height: 100px;
  /* 使用text-align属性让文字左右居中 */
  text-align: center;
  margin-bottom: 10px;
  background-color: #d5e8d4;
  /* 使用行高让文字上下居中 */
  line-height: 100px;
}

.box2 {
  display: none;
}
```

### display:inline/inline-block

#### 行内元素可以设置padding

```css
a {
  background-color: #fff2cc;
  padding: 20px;
}
```

#### 行内元素可以设置左右margin，不能设置上下margin

```html
<a href="#">点击跳转到</a>
<span>优课达</span>
<div></div>
```

```css
a {
  margin-left: 40px;
  margin-right: 30px;
  margin-top: 400px;
  margin-bottom: 400px;
}

span {
  margin-left: 20px;
}

div {
  width: 300px;
  height: 50px;
  background-color: #b0e3e6;
}
```

#### inline-block

**可以在同一行显示的块元素**

##### 去除空白折叠现象（去除回车）

```html
<!-- 将div标签写在一行 -->
<div class="box1"></div><div class="box2"></div>
```

```css
div {
  width: 200px;
  height: 50px;
  display: inline-block;
}

.box1 {
  background-color: #fff2cc;
}

.box2 {
  background-color: #b0e3e6;
}
```

##### 给父元素添加word-spacing属性

单词与单词之间的距离，这个距离写成负值，一般写小于-20px的值

```html
<div class="father">
  <div class="box1"></div>
  <div class="box2"></div>
</div>
```

```css
.father {
  word-spacing: -50px;
}

.box1 {
  width: 200px;
  height: 50px;
  display: inline-block;
  background-color: #fff2cc;
}

.box2 {
  width: 200px;
  height: 50px;
  display: inline-block;
  background-color: #b0e3e6;
}
```

##### 给父元素设置font-size：0px

回车当作是一个文字，如果将文字设置为0，空袭自然会消失

```html
<div class="father">
  <div class="box1"></div>
  <div class="box2"></div>
</div>
```

```css
.father {
  font-size: 0px;
}

.box1 {
  width: 200px;
  height: 50px;
  display: inline-block;
  background-color: #fff2cc;
}

.box2 {
  width: 200px;
  height: 50px;
  display: inline-block;
  background-color: #b0e3e6;
}
```

#### 综合应用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>案例</title>
    <link rel="stylesheet" href="./index.css">
</head>

<body>
  <ul class="head">
    <li class="head-first">商品分类</li>
    <li class="head-second">天猫双十一</li>
  </ul>

  <ul class="list">
    <li><a href="#">大牌女装</a></li>
    <li><a href="#">运动户外</a></li>
    <li><a href="#">潮流男装</a></li>
    <li><a href="#">美妆洗护</a></li>
    <li><a href="#">母婴好货</a></li>
    <li><a href="#">数码家电</a></li>
    <li><a href="#">家具建材</a></li>
    <li><a href="#">全球尖货</a></li>
    <li><a href="#">苏宁易购</a></li>
    <li><a href="#">汽车用品</a></li>
  </ul>
</body>

</html>
```

```css
ul,
li {
  list-style: none;
  padding: 0px;
  margin: 0px;
}
/* 浏览器都有自己的默认样式，以上内容用于浏览器默认样式的清除 */

.head {
  width: 200px;
  color: #ffffff;
  /* 去除空白折叠 */
  font-size: 0px;
}

.head li {
  /* 让两个li处于同一行 */
  display: inline-block;
  font-size: 12px;
  line-height: 36px;
  width: 100px;
  text-align: center;
}

.head .head-first {
  background-color: #c60a0a;
}

.head .head-second {
  background-color: #464444;
}

.list {
  width: 200px;
  box-sizing: border-box;
  padding-top: 29px;
  padding-bottom: 14px;
  background-color: #413f3f;
}

.list li {
  margin-bottom: 14px;
  padding-left: 24px;
  padding-right: 24px;
}

.list li a {
  /* 让a成为块状元素才能让宽度占据整条li */
  display: block;
  border: 1px solid #cb0c10;
  border-radius: 10px;
  text-align: center;
  line-height: 29px;
  /* a标签比较特殊，设置它的文本样式需要直接选中它 */
  color: #ffffff;
  /* 去除a标签的下划线 */
  text-decoration: none;
}

```

## css-定位

### position的常用值

1. static（遵循默认的文档流布局）
2. relative（相对定位）
3. absolute（绝对定位）
4. fixed（固定定位）
5. sticky（粘性定位）

#### relative

相对于原来图片的位置进行移动

#### absolute

**absolute（绝对定位）和relation（相对定位）的区别，relation是相对自己进行top、left、right、bottom进行偏移，而abslute是寻找最近的非static的祖先节点进行偏移**



#### fixed

在很多场景下，文章的标题会一直停留在浏览器的底部，不会随着页面的滚动而消失，这时候就要用到fixed

固定定位和绝对定位类似，但元素的包含块为屏幕视口（viewport）

固定定位不为元素预留空间，而是通过指定元素相对于屏幕视口的位置来指定元素位置，元素的位置在屏幕滚动时不会改变。

问题：继续滚动到图片时，被图片区域遮挡

解决：

#### z-index

决定图层的优先级

1. 默认非static元素的z-index都为0
2. z-index越大，则越在最上面，离观察者越近
3. 同样的z-index，在html中的元素越靠后，则越在最上面，离观察者越近

**为了解决被遮挡的问题，只需要修改z-index的值即可**

#### 综合应用

```html
<!DOCTYPE html>
<head>
  <meta charset="utf-8" />
  <link rel="stylesheet" type="text/css" href="./index.css" />
  <title>优课达</title>
</head>
<body>
  <h1 class="title">MOUNTAIN</h1>
  <p>
    The Facebook post was heartfelt. We like our little town just as it is:
    Little. Homey. Just us’ns.
  </p>

  <div class="img-box">
    <div class="img-item">
      <img
        class="first"
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/1.jpg?x-oss-process=image/resize,h_300"
      />
      <span>图片1</span>
    </div>
    <div class="img-item">
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/2.jpg?x-oss-process=image/resize,h_300"
      />
      <span>图片2</span>
    </div>
    <div class="img-item">
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/3.jpg?x-oss-process=image/resize,h_300"
      />
      <span>图片3</span>
    </div>
    <div class="img-item">
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/4.jpg?x-oss-process=image/resize,h_300"
      />
      <span>图片4</span>
    </div>
  </div>

  <h2>LISTEN</h2>
  <p>
    Listen, I can empathize. As someone who’s lived in the Denver area since
    1971 — right about the time John Denver’s songs were enticing folks to move
  </p>
  <footer></footer>
</body>

```

```css
body {
    margin: 0; /*去掉默认的样式*/
    font-family: Sans-serif;
    color: rgba(0, 0, 0, 0.84);
    font-size: 16px;
    padding: 30px;
  }
  
  img {
    width: 100%;
  }
  
  .img-item {
    position: relative;
  }
  
  .img-item > span {
    position: absolute;
    right: 10px;
    top: 10px;
    font-size: 20px;
    color: yellow;
  }
  
```

## Float

css中最常用的布局属性，使用它可以让元素靠左或者靠右排版

**两个HTML5的标签**

nav：一般用于表示此区块是导航区域

main：一般用户表示此区域是网页的主题区域 

```html
<!DOCTYPE html>
<html>
  <head>
    <title>优课达</title>
    <link rel="stylesheet" type="text/css" href="./index.css" />
  </head>
  <body>
    <nav></nav>
    <main>
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/1.jpg?x-oss-process=image/resize,h_500"
      />
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/2.jpg?x-oss-process=image/resize,h_500"
      />
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/3.jpg?x-oss-process=image/resize,h_500"
      />
      <img
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/4.jpg?x-oss-process=image/resize,h_500"
      />
    </main>
  </body>
</html>
```

codesign操作：https://www.bilibili.com/video/BV18Q4y1r7D5/

### 定位实战

#### 什么是模态框：

1. 模态框总是在浏览器的中心，浏览器随意放大缩小，模态框还是在浏览器中心
2. 模态框总是有一个半透明的背景

```css
.mask {
  position: fixed; /*1*/
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.7); /*2*/
}
```

1. 通过fixed，上下左右都为0.设置mask是撑满整个屏幕的
2. background-color我们使用了rgba颜色设置方法，最后一位可以设置颜色透明度

#### 完成模态框内部

```html
<!DOCTYPE html>
<head>
  <link rel="stylesheet" type="text/css" href="./index.css" />
</head>
<body>
  <nav class="nav">
    ……
  </nav>
  <main>
    ……
  </main>
  <div class="mask"></div>
  <div class="modal">
    <img src="https://style.youkeda.com/img/ykd-components/logo.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" />
  </div>
</body>
```

```css
.modal {
  background-color: #fff;

  /* 设置长宽 */
  width: 300px;
  height: 150px;

  /* 设置圆角20px */
  border-radius: 20px;
}

.modal > img {
  display: block;
  width: 200px;
  margin: 39px auto; /*1*/
}
```

**元素水平居中**

1. 行内元素：text-align:center

2. 块状元素：margin:0 auto  如果不是块状元素需要设置 display：block

#### 完成模态框布局

```css
.modal {
  position: fixed; /*1*/
  left: 50%; /*2*/
  top: 50%; /*3*/
  background-color: #fff;

  /* 设置长宽 */
  width: 300px;
  height: 150px;

  /* 设置圆角20px */
  border-radius: 20px;
}

.modal > img {
  display: block;
  width: 200px;
  margin: 39px auto;
}
```

**通过上面步骤可以初步将modal居中，但是会往右下偏移部分**

这种情况通过margin进行修正

```css
.modal {
  position: fixed;
  left: 50%;
  top: 50%;

  margin-left: -150px; /*1*/
  margin-top: -75px; /*2*/

  background-color: #fff;

  /*设置长宽*/
  width: 300px;
  height: 150px;

  /*设置圆角20px*/
  border-radius: 20px;
}
```

### 综合应用

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" type="text/css" href="./index.css" />
    <title>优课达</title>
  </head>
  <body>
    <div>
      <div class="mask">
      <img class="logo"
      alt=""
      src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/combat-1-modal/9.svg"
      >
      <span class="instance">学得比别人好一点</span>
      <img class="weixin"
      alt=""
      src="https://style.youkeda.com/img/pizza/weixin.png"
      >
      <span class="Wlogin">微信登录</span>
      <img class="qq"
      alt=""
      src="https://style.youkeda.com/img/pizza/qq.png"
      >
      <span class="Qlogin">QQ登录</span>
      <img class="sep1"
      alt=""
      src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/combat-1-modal/sep.png"
      >        
      <img class="sep2"
      alt=""
      src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/combat-1-modal/sep.png"
      > 
      <span  class="login">请选择登录方式</span>
      </div>

    </div>
  </body>
</html>

```

```css
html,
body {
  height: 100%;
  margin: 0;
}

ul,
li {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}

h1,
h2 {
  margin: 0;
}

p {
  margin: 0;
  padding: 0;
}

/* 浏览器都有自己的默认样式，以上部分为清除浏览器默认样式 */

html,
body {
  width: 100%;
  height: 100%;
}
body {
  background-image: url(https://document.youkeda.com/P3-1-HTML-CSS/1.8/login-bg.svg);
  background-size: cover;
}

.mask{
  position: fixed;
  left: 50%;
  top: 50%;
  margin-left: -245px; /*1*/
  margin-top: -201px; /*2*/
  background-color: #ffffff;
  width: 490px;
  height: 403px;
  border-radius: 16px;
}
.logo{
  position: absolute;
  width: 177.97px;
  height: 64px;
  left: 155.03px;
  top: 62px;
}
.weixin{
  position: absolute;
  width: 64px;
  height: 64px;
  left: 116px;
  bottom: 82px;
}
.qq{
  position: absolute;
  width: 64px;
  height: 64px;
  right: 116px;
  bottom: 82px;
}
.sep1{
  position: absolute;
  width: 163px;
  height: 1px;
  top: 209px;
  left: 20px;
}
.sep2{
  position: absolute;
  width: 163px;
  height: 1px;
  top: 209px;
  right: 20px;
}
.instance{
  position: absolute;
  width: 171.3px;
  height: 20px;
  font-size: 14px;
  color: #3A3A3A;
  line-height: 20px;
  letter-spacing: 7.3px;
  left: 163px;
  top: 140px;
  text-align:center;
}
.login{
  position: absolute;
  width: 84px;
  height: 17px;
  font-size: 12px;
  line-height: 17px;
  left: 203px;
  top: 200px;
  text-align: center;
}
.Wlogin{
  position: absolute;
  width: 64px;
  height: 22px;
  left: 116px;
  bottom: 40px;
  font-size: 16px;
  color: #292929;
  line-height: 22px;
  text-align: center;
}
.Qlogin{
  position: absolute;
  width: 64px;
  height: 22px;
  right: 116px;
  bottom: 40px;
  font-size: 16px;
  color: #292929;
  line-height: 22px;
  text-align: center;

}
```

## 背景颜色

```css
background: linear-gradient(to right,#95ca47,#4dc891);
```

linear-gradient:渐变类型（线性渐变)

to right: 渐变方向

开始颜色  结束颜色

### 渐变方向

to right /to left:向右/向左渐变

to top / to bottom  向上/向下渐变

to right bottom / to right top  向右下/向右上渐变

xxxdeg    xxx范围（0到360）更精确的渐变方向

### 渐变位置

渐变不一定是从开始到结束，我们可以设置各种中间状态

我们可以在每个色值后面跟一个值 （百分比、px）来约定变色起止位置

多颜色渐变：https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Using_CSS_gradients

### 综合应用

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <link rel="stylesheet" type="text/css" href="./index.css" />
    <title>每日推荐</title>
  </head>
  <body>
    <div class="box">
      <div class="head">星期二</div>
      <div class="date">17</div>
      <div class="mask"></div>
    </div>
  </body>
</html>

```

```css
.box{
  position: relative;
  width: 140px;
  height: 140px;
  border-radius: 4px;
}
.box>.head{
  width: 100%;
  height: 33px;
  background: linear-gradient(to bottom,#d94747,#b9191a);
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
  font-size: 14px;
  color: #fed9d9;
  line-height: 33px;
  text-align: center;
}
.box>.date{
  width: 100%;
  height: 107px;
  color: #202020;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 97px;
  font-weight: bold;
  line-height: 107px;
  text-align: center;
}
.mask{
  position: absolute;
  top: 33px;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.05),
      rgba(0, 0, 0, 0.15) 50%,
      rgba(0, 0, 0, 0.05) 50%,
      rgba(0, 0, 0, 0.15) 100%
    );

  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
}
```

## 背景图片的设置

注意：地址不需要用引号包裹

```css
background-image: url(远程或者本地图片地址);
```

### 背景图片出现重复

当背景图片长宽任意一项小于容器的长宽，默认css会让图片重复，直到铺满整个容器位置

解决：

```css
background-repeat: no-repeat;
```

***background-repeat的值***

repeat：默认值，会出现重复

repeat-x：只在水平方向出现重复

repeat-y：只在垂直方向出现重复

no-repeat：不出现重复

### 背景图片不居中

默认情况下，背景图片是从容器的左上角开始布局，为了让容器垂直水平居中，我们可以

```css
background-position: center;
```

```css
/*完整图片布局*/
.box {
  width: 350px;
  height: 250px;
  border: 1px solid #e8e8e8;
  font-size: 30px;
  font-weight: bold;
  color: yellowgreen;

  background-image: url(https://style.youkeda.com/img/ykd-components/logo.png);
  background-repeat: no-repeat;
  background-position: center;
  }
```

***background-position的值***

![image-20230529100820181](图片/image-20230529100820181.png)

### 背景图片撑满整个容器

***background-size的值***

![image-20230529101023781](图片/image-20230529101023781.png)

### 综合

```css
.box {
  width: 350px;
  height: 250px;
  border: 1px solid #e8e8e8;
  font-size: 30px;
  font-weight: bold;
  color: yellowgreen;

  background-image: url(https://style.youkeda.com/img/ykd-components/logo.png);
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
```

#### 四个属性进行合并

```css
.box {
  width: 350px;
  height: 250px;
  border: 1px solid #e8e8e8;
  font-size: 30px;
  font-weight: bold;
  color: yellowgreen;

  background: url(https://style.youkeda.com/img/ykd-components/logo.png)
    no-repeat center / contain;
}
```

### 综合运用1

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <link rel="stylesheet" type="text/css" href="./index.css" />
    <title>每日推荐</title>
  </head>
  <body>
    <div class="back">
      <div class="box">
      <div class="head">星期二</div>
      <div class="date">17</div>
      <div class="mask"></div>
      </div>
    </div>
  </body>
    
</html>

```

```css
.back{
  width: 715px;
  height: 200px;
  background: url(https://document.youkeda.com/P3-1-HTML-CSS/1.9/music-bg.jpg)
  no-repeat center / contain;
}
.box {
  position: relative;
  left: 48px;
  top: 30px;
  width: 140px;
  height: 140px;
  border-radius: 4px;
  overflow: hidden;
}

.head {
  height: 33px;
  line-height: 33px;
  color: #fed9d9;
  font-size: 14px;
  text-align: center;
  background: linear-gradient(to bottom, #d94747, #b9191a);
}

.date {
  background-color: white;
  height: 107px;
  line-height: 107px;
  text-align: center;
  font-size: 94px;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: bold;
  color: #202020;
}

.mask {
  position: absolute;
  top: 33px;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.05),
    rgba(0, 0, 0, 0.15) 50%,
    rgba(0, 0, 0, 0.05) 50%,
    rgba(0, 0, 0, 0.15) 100%
  );
}

```

### 综合运用2

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" type="text/css" href="./index.css" />
  <title>微博</title>
</head>
<body>
  <div class="banner">
    <div class="main">
      <div class="info">
        <div class="title">
          #一直单身但颜值超高的人#
        </div>
        <div class="ext">
          <span class="discuss">1.4万讨论</span>
          <span class="read">2443.3万阅读</span>
        </div>
      </div>
    </div>
  </div>
</body>

```

```css
.banner {
    position: relative;
    width: 600px;
    height: 300px;
    background-image: url(https://document.youkeda.com/P3-1-HTML-CSS/1.9/weibo-banner.jpg);
    background-size: cover;
  }
  
  .info {
    float: left;
  }
  
  .main {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 60px;
    padding-left: 10px;
    color: #fff;
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.9));
  }
  
  .title {
    margin-top: 10px;
    font-size: 18px;
    font-weight: 700;
    line-height: 20px;
  }
  
  .ext {
    margin-top: 4px;
    font-size: 12px;
    line-height: 20px;
  }
  
  .discuss {
    margin-right: 20px;
  }
  
```

大作业

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" type="text/css" href="./index.css" />
    <title>QQ注册</title>
  </head>
  <body>
    <nav class="nav">
      <a class="qq">
        <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/qq.png" />
        <span>QQ</span>
      </a>
      <ul class="right">
        <li class="bright">
          <img
            src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/bright.png"
            alt="QQ靓号"
          />
        </li>
        <li class="language">
          <span>简体中文</span>
          <img
            class="arrow"
            src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/arrow-down.png"
          />
        </li>
        <li class="contact">意见反馈</li>
      </ul>
    </nav>
    <main>
      <div class="back">
         <img src="http://document.youkeda.com/P3-1-HTML-CSS/1.11/bg.png">
      </div>
      <div class="box">
        <span class="welcome">欢迎注册QQ</span>
        <span class="happy">每一天，乐哉沟通。</span>
        <span class="free">免费靓号</span>
        <div class="nicheng">
          <input placeholder="昵称">
        </div>
        <div class="password">
          <input placeholder="密码">
        </div>
        <div class="tishi">
          <input placeholder="+86">
        </div>
        <div class="phone">
          <input placeholder="手机号码">
        </div>
        <span></span>
      </div>
    </main>
  </body>
</html>

```

```css
html,
body {
  height: 100%;
  margin: 0;
}

ul,
li {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}

h1,
h2 {
  margin: 0;
}

p {
  margin: 0;
  padding: 0;
}

/* 浏览器都有自己的默认样式，以上部分为清除浏览器默认样式 */
.back>img{
  width: 480px;
  height: 800px;
}

.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  padding: 0 20px;
}

a.qq {
  margin-left: 10px;
  margin-top: 20px;
  float: left;
  cursor: pointer;
  font-size: 0;
}

a.qq > img {
  width: 40px;
  height: 40px;
  vertical-align: middle;
}

a.qq > span {
  vertical-align: middle;
  font-size: 36px;
  line-height: 43px;
  margin-left: 6px;
}

ul.right {
  float: right;
}

ul.right > li {
  float: left;
  margin-top: 20px;
  margin-right: 40px;

  font-size: 16px;
  line-height: 24px;

  cursor: pointer;
}

.bright {
  width: 95px;
  height: 34px;
}

.bright > img {
  width: 100%;
  height: 100%;
}

ul.right > li.language {
  font-size: 0;
  margin-top: 30px;
}

ul.right > li.language span {
  font-size: 16px;
  vertical-align: middle;
}

ul.right > li.language .arrow {
  vertical-align: middle;
  width: 12px;
  height: 8px;
}

ul.right > li.contact {
  margin-top: 30px;
}

/*上面是QQ注册页头部CSS*/
.box{
  width: calc(1440px - 480px);
  height: 800px;
}
.box>.welcome{
  position: absolute;
  left: 720px;
  top: 104px;
  width: 270px;
  height: 62px;
  color: #000000;
  font-size: 44px;
  font-weight: 400; 
  line-height: 62px;
  font-family: "PingFang SC";
  text-align: left;
}
.box>.happy{
  position: absolute;
  left: 720px;
  top: 179px;
  width: 252px;
  height: 34px;
  color: #333333ff;
  font-size: 27px;
  font-weight: 400;
  font-family: "PingFang SC";
  text-align: left;
  line-height: 33.6px;
}
.box>.free{
  position: absolute;
  width: 96px;
  height: 29px;
  left: 1104px;
  top: 182px;
  color: #359effff;
  font-size: 23px;
  font-weight: 700;
  font-family: "PingFang SC";
  text-align: left;
  line-height: 28.8px;
}
.nicheng{
  position: absolute;
  float: left;
  left: 720px;
  top: 276px;
}
.nicheng>input{
width: 480px;
height: 52px;
border: 1px solid #AAAAAA;
border-radius: 4px;
opacity: 1;
padding-left: 20px;
color: #aaaaaaff;
font-size: 19px;
font-weight: 400;
font-family: "PingFang SC";
text-align: left;
line-height: 20px;
}
.password{
  position: absolute;
  float: left;
  left: 720px;
  top: 360px;
}
.password>input{
  width: 480px;
  height: 52px;
  border: 1px solid #AAAAAA;
  border-radius: 4px;
  opacity: 1;
  padding-left: 20px;
  color: #aaaaaaff;
  font-size: 19px;
  font-weight: 400;
  font-family: "PingFang SC";
  text-align: left;
  line-height: 20px;
  }
  .tishi{
    position: absolute;
    float: left;
    left: 720px;
    top: 444px;
  }
  .tishi>input{
  width: 154px;
  height: 52px;
  border: 1px solid #AAAAAA;
  border-radius: 4px;
  opacity: 1;
  padding-left: 14px;
  color: #000000;
  font-size: 20px;
  font-weight: 700;
  font-family: "PingFang SC";
  text-align: left;
  line-height: 43px;
  }
  .phone{
    position: absolute;
    float: left;
    left: 893px;
    top: 444px;
  }
  .phone>input{
  width: 288px;
  height: 52px;
  margin-left: 19px;
  border: 1px solid #AAAAAA;
  border-radius: 4px;
  opacity: 1;
  padding-left: 20px;
  color: #aaaaaaff;
  font-size: 19px;
  font-weight: 400;
  font-family: "PingFang SC";
  text-align: left;
  line-height: 20px;
  }

  

```

