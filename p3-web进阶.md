# p3-web进阶

## HTML5/CSS3介绍

**语义化标签**

```html
<!-- 头部 -->
<header>header</header>
<!-- 主体 -->
<main>
    <!-- 导航 -->
    <nav>nav</nav>
    <!-- 区块 -->
    <section>section</section>
    <section>section</section>
</main>
<!-- 侧边栏 -->
<aside></aside>
<!-- 底部 -->
<footer></footer>
```

## css伪元素--::after/::before

 

```html
<span class="icon"></span><span class="words">主页</span>
```

```css
.icon {
    display: inline-block;
    width: 24px;
    height: 24px;
    background: url(https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-2-HTML-CSS/1.2/source/first-page.png) no-repeat center;
    background-size: contain;
    vertical-align: top;
    margin-right: 8px;
}

.words {
    font-size: 18px;
    line-height: 24px;
}
```

**伪元素就是利用css代码在标签内部的前面，或者后面添加一个行内元素，这个行内元素你可以理解为span**

```css
/* before */
选择器::before{
  /* 使用空白符号占位 */
  content: '';
}

/* after */
选择器::after{
  /* 使用空白符号占位 */
  content: '';
}
```

实例：

```css
/* 在span之前添加行内元素 */
span::before {
  content: '';
  /* 将添加的行内元素定位，并设置大小、背景 */
    position: absolute;
    left: 0px;
    width: 24px;
    height: 24px;
    background: url(https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-2-HTML-CSS/1.2/source/first-page.png) no-repeat center;
    background-size: contain;
}
```

### 综合运用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <div class="banner">
        <!--可以使用列表完成小圆点的绘制，注意清除列表样式-->
        <ul>
            <li class="one"></li>
            <li class="two"></li>
            <li class="third"></li>
            <li class="four"></li>
            <li class="five"></li>
        </ul>
    </div>
</body>

</html>
```

```css
* {
    margin: 0px;
    padding: 0px;
}

.banner {
    position: relative;
    width: 850px;
    height: 394px;
    background: url(./images/banner.png) no-repeat center;
    background-size: contain;
}

.banner::before {
    /*在这里使用伪元素完成左箭头*/
    content: '';
    position: absolute;
    left: 8px;
    top: 157px;
    width: 30px;
    height: 30px;
    background: url(./images/left.png) no-repeat center;
    background-size: contain;
}

.banner::after {
    /*在这里使用伪元素完成右箭头*/
    content: '';
    position: absolute;
    right: 8px;
    top: 157px;
    width: 30px;
    height: 30px;
    background: url(./images/right.png) no-repeat center;
    background-size: contain;
}
ul
,li{
    list-style: none;
}
.one{
position: absolute;
left: 721px;
top: 339px;
width: 8px;
height: 8px;
opacity: 1;
border-radius: 50%;
background: #9995a5ff;
}
.two{
position: absolute;
left: 737px;
top: 339px;
width: 8px;
height: 8px;
opacity: 1;
border-radius: 50%;
background: #9995a5ff;
}
.third{
position: absolute;
left: 753px;
top: 339px;
width: 8px;
height: 8px;
opacity: 1;
border-radius: 50%;
background: #9995a5ff;
}
.four{
    position: absolute;
left: 769px;
top: 339px;
width: 8px;
height: 8px;
opacity: 1;
border-radius: 50%;
background: #9995a5ff;
}
.five{
    position: absolute;
left: 785px;
top: 339px;
width: 8px;
height: 8px;
opacity: 1;
border-radius: 50%;
background: #9995a5ff;
}
li::before{
content: '';
box-sizing: border-box;
margin: 2px 2px;
padding: 2px;
display: block;
width: 4px;
height: 4px;
opacity: 1;
border-radius: 50%;
background: #666278ff;
}
.third::before{
    content: '';
    box-sizing: border-box;
margin: 1px 1px;
padding: 1px;
display: block;
width: 6px;
height: 6px;
opacity: 1;
background: #D6D6D6;
border-radius: 50%;
}

```

### css伪类--清除浮动

清除浮动的方法很多，这里我们只需要掌握一种最常用的方法即可

```css
.clearfix::after{
  content: '';
  display: block;
  clear: both;
}
```

**例子**

重点

```css
.clearfix:after {
  visibility: hidden;
  display: block;
  font-size: 0;
  content: " ";
  clear: both;
  height: 0;
}
```

```html
<!-- 添加清除浮动类名 -->
<div class="father-one clearfix">
    <div class="son-one">son-one</div>
    <div class="son-two">son-two</div>
    <div class="son-three">son-three</div>
</div>
```

<u>***注意：哪个盒子有浮动，就在哪个盒子上添加清楚浮动***</u>

**为了去除最后一个元素的边距，防止换行**

```css
.last{
  margin-right:0;
}
```

### 综合应用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <!-- 不要忘记引入index.css -->
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <section class="phone"></section>
    <main>
        <span class="name">小米&lt;小爱老师&gt;</span>
        <span class="content">口袋里的英语外教</span>
        <span class="price">499元起</span>
    </main>

</body>

</html>
```

```css
/* 清除所有的内外边距 */
* {
    margin: 0;
    padding: 0;
}
body{
    position: relative;
    width: 200px;
height: 256px;
opacity: 1;
background: #ffffffff;
}
.phone{
    position: absolute;
    left: 35px;
    top: 22px;
    width: 130px;
height: 130px;
opacity: 1;
background: url(./images/phone.jpg) no-repeat center;
background-size: contain;

}
.name{
    position: absolute;
    left: 56px;
    top: 168px;
width: 90px;
height: 17px;
opacity: 1;
color: #000000ff;
font-size: 12px;
font-weight: 400;
font-family: "PingFang SC";
text-align: left;
line-height: 17px;
}
.content{
    position: absolute;
    left: 52px;
    top: 189px;
    width: 96px;
height: 17px;
opacity: 1;
color: #a8a8a8ff;
font-size: 12px;
font-weight: 400;
font-family: "PingFang SC";
text-align: left;
}
.price{
    position: absolute;
    left: 77px;
    top: 214px;
    width: 46px;
height: 17px;
opacity: 1;
color: #fd6821ff;
font-size: 12px;
font-weight: 500;
font-family: "PingFang SC";
text-align: left;
}

```

### 大作业

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <section class="section-goods">
        <main class="main-good-list">
            <!--商品头部-->
            <header class="clearFix">
                <div class="title-left">
                    智能
                </div>
                <ul class="title-right">
                    <li class="selected">智能</li>
                    <li>安防</li>
                    <li>出行</li>
                </ul>
            </header>

            <!--商品列表-->
            <ul class="box-goods">
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li class="last">
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
            </ul>
            <ul class="goods-list">
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li>
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
                <li class="last">
                    <div class="phone"></div>
                    <div>
                        <span class="name last">小米&lt;小爱老师&gt;</span>
                        <span class="content">口袋里的英语外教</span>
                        <span class="price">499元起</span>
                    </div>
                </li>
            </ul>

        </main>
    </section>
    <footer class="foot">
    </footer>
</body>

</html>
```

```css
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}


ul {
  list-style: none;
}

.clearFix::after {
  content: '';
  display: block;
  clear: both;
}

.section-goods {
  position: relative;
  width: 1439px;
  height: 716px;
  background: #F5F5F5;
}

.main-good-list {
  width: 1048px;
  margin: 0 auto;
}

/*商品头部*/
.title-left {
  float: left;
  color: #000000;
  font-size: 20px;
  line-height: 54px;
}

.title-right {
  float: right;
}

.title-right>li {
  position: relative;
  box-sizing: border-box;
  float: left;
  margin-left: 20px;
  line-height: 54px;
  color: #999999;
  font-size: 16px;
}

.title-right>li.selected {
  margin-left: 0px;
  color: #FD6821;
}

.title-right>li.selected::after {
  content: '';
  position: absolute;
  bottom: 11px;
  left: 1px;
  width: 30px;
  height: 2px;
  background: #FD6821;
}
.box-goods{
  position: absolute;
  left: 196px;
  top: 56px;
  width:1048px;
}
.box-goods>li{
  position: relative;
  float: left;
  box-sizing: border-box;
  margin-right: 12px;
  width: 200px;
  height: 256px;
  background: #ffffff;
}
.box-goods>.last{
  margin-right: 0;
}
.goods-list{
  position: absolute;
  left: 196px;
  top: 324px;
  width:1048px;
}
.goods-list>li{
  position: relative;
  float: left;
  box-sizing: border-box;
  margin-right: 12px;
  width: 200px;
  height: 256px;
  background: #ffffff;
}
.goods-list>.last{
  margin-right: 0;
}
.phone{
  position: absolute;
  left: 35px;
  top: 22px;
  width: 130px;
height: 130px;
opacity: 1;
background: url(./images/phone.jpg) no-repeat center;
background-size: contain;

}
.name{
  position: absolute;
  left: 56px;
  top: 168px;
width: 90px;
height: 17px;
opacity: 1;
color: #000000ff;
font-size: 12px;
font-weight: 400;
font-family: "PingFang SC";
text-align: left;
line-height: 17px;
}
.content{
  position: absolute;
  left: 52px;
  top: 189px;
  width: 96px;
height: 17px;
opacity: 1;
color: #a8a8a8ff;
font-size: 12px;
font-weight: 400;
font-family: "PingFang SC";
text-align: left;
}
.price{
  position: absolute;
  left: 77px;
  top: 214px;
  width: 46px;
height: 17px;
opacity: 1;
color: #fd6821ff;
font-size: 12px;
font-weight: 500;
font-family: "PingFang SC";
text-align: left;
}

.foot{
  position: absolute;
  left: 196px;
  top:612px;
width: 1048px;
height: 103px;
opacity: 1;
background: url(./images/book.jpg) no-repeat center;
background-size: contain;
}
```

### CSS伪类---事件伪类

我们学习的是鼠标移动上去的效果--hover

当鼠标移动上去以后，对应的地方，样式会发生改变

```css
li:hover{
    background-color: #47A0FC;
    color: white;
}
```

#### active--鼠标点击时

active：鼠标点击效果，这个效果在超链接比较常见，注意这里的点击是点住鼠标不松开

**首先需要用选择器选中要添加伪类的标签，然后在选择器后面添加对应的伪类，这里我们添加的是active**

```css
ul>li:active{
    /* 要改变的效果 */
}
```

```css
ul>li:active{
    /* 要改变的效果 */
    color: black;
}
```

注意：hover一定要在active之前，否则不会生效

```css
/* 正确 */
a:hover{}
a:active{}
/* 错误 */
a:active{}
a:hover{}
```

#### focus--获取焦点后

focus：获取焦点的伪类，一般用于具有焦点的元素，比如：input。比如我们可以让input获取到焦点以后，改变input的边框颜色。

```css
input{
border: 1px solid #fff;
}
input::focus{
border:1px solid #000;
}
```

#### 综合应用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css" type="text/css" media="all" />
</head>

<body>
    <div class="search-box">
        <input type="text" value="红米k20">
        <div class="select-list">
            <ul>
                <li>小米9</li>
                <li>Redmi K20 pro</li>
                <li>Redmi K20 </li>
                <li>Redmi note 7 Pro </li>
                <li>Redmi note 7</li>
                <li>小米电视4c</li>
                <li>电视32英寸</li>
                <li>笔记本Pro</li>
                <li>小爱音箱</li>
                <li>净水器</li>
            </ul>
        </div>
        <div class="search-btn">
            <span></span>
        </div>

    </div>
</body>

</html>
```

```css
body {
    margin: 0;
    background-color: #fff;
}

ul,
li {
    margin: 0px;
    padding: 0px;
    list-style: none;
}

.search-box {
    position: relative;
    box-sizing: border-box;
    width: 254px;
    height: 42px;
    background: #FFFFFF;
    border: 1px solid #E0E0E0;
}

.search-box>input {
    box-sizing: border-box;
    float: left;
    border: none;
    height: 40px;
    width: 209px;
    padding-left: 20px;
    outline: none;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 17px;
    color: #AEAEAE;
}

.search-box .search-btn {
    float: right;
    height: 42px;
    width: 42px;
    border: 1px solid #E0E0E0;
    box-sizing: border-box;
    margin-top: -1px;
    margin-right: -1px;
    padding: 12px;
}

.search-box>div>span {
    display: block;
    width: 16px;
    height: 16px;
    background: url(./images/search-normal.png) no-repeat center;
    background-size: contain;
}

.search-box .select-list {
    position: absolute;
    top: 40px;
    left: -1px;
    width: 213px;
    height: 282px;
    background: #FFFFFF;
    border: 1px solid #FD6821;
    box-sizing: border-box;
    display: none;
}

.search-box .select-list li {
    height: 28px;
    font-weight: normal;
    font-size: 12px;
    color: #000000;
    padding-left: 15px;
    line-height: 28px;
}


.search-box:hover {
    border: 1px solid #FD6821;
}

.search-box:hover .search-btn {
    border: 1px solid #FD6821;
}

.search-box input:focus+.select-list {
    display: block;
}
```

**如何通过兄弟元素的伪类改变另一个兄弟元素的属性**

```html
<div>
    <input type="text">
    <div></div>
</div>
```

```css
/* 选中获得焦点的 input 元素后面一个 div 元素（input 和 div 是兄弟元素） */
input:focus+div{
    border:1px solid blue;
}
```

<u>注意：被改变的元素要紧邻有伪类效果的元素</u>

### 列表伪类

#### 匹配其父元素的第一个子元素---:first-child

具体做法：在文首效果图的基础代码上添加如下代码

```css
ul>li:first-child{
    background-color: #3687FC;
    color: #FFFFFF;
}
```

#### 匹配父元素中最后一个子元素---：last-child



#### 匹配父元素中第n个子元素--：nth-child（）

括号里填第几个元素，还可以写两个特定单词（odd（奇数），even（偶数））

```css
ul>li:nth-child(3){
  background-color: #3687FC;
  color: #FFFFFF;
}
```

#### 综合应用

***<u>重点：列表伪类的使用和伪元素的使用</u>***

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <!-- 不要忘记引入index.css -->
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <div class="box">
        <ul>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>

    </div>

</body>

</html>
```

```css
* {
    margin: 0;
    padding: 0;
}
ul,li{
    list-style: none;
}
.box{
    position: relative;
    width: 1439px;
    height: 199px;
    opacity: 1;
    background: #ffffffff;
}
ul>li{
    float: left;
    width: 126px;
height: 141px;
background: #c4c4c4ff;
}
ul>li:first-child{
position: absolute;
left: 215px;
top: 29px;
}
ul>li:nth-child(2){
    position: absolute;
left: 391px;
top: 29px;

}
ul>li:nth-child(3){
    position: absolute;
left: 568px;
top: 29px;
    
}
ul>li:nth-child(4){
    position: absolute;
left: 745px;
top: 29px;
    
}
ul>li:nth-child(5){
    position: absolute;
left: 922px;
top: 29px;
    
}
ul>li:last-child{
position: absolute;
left: 1099px;
top: 29px;
}
li::after{
    content: '';
    position: absolute;
    left: 151px;
    width: 1px;
height: 86px;
background: #dfdfdfff;
}
li:last-child::after{
    width: 0;
}

```

大作业;

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <div class="banner">
        <ul class="clearFix">
            <li>
                <div></div>
                <p>小米笔记本Pro 15.6</p>
                <h4>5599元起</h4>
            </li>
            <li>
                <div></div>
                <p>RedmiBook 14</p>
                <h4>3999元起</h4>
            </li>
            <li>
                <div></div>
                <p>游戏本2019款</p>
                <h4>7499元起</h4>
            </li>
            <li>
                <div></div>
                <p>小米笔记本Pro 15.6</p>
                <h4>4299元起</h4>
            </li>
            <li>
                <div></div>
                <p>小米笔记本Air 12.5</p>
                <h4>3499元起</h4>
            </li>
            <li>
                <div></div>
                <p>小米笔记本Air 13.3</p>
                <h4>4499元起</h4>
            </li>
        </ul>
    </div>
</body>

</html>
```

```css
* {
    margin: 0;
    padding: 0;
}

body {
    background: #c4c4c4;
}

.clearFix::after {
    content: '';
    display: block;
    clear: both;
}

.banner {
    width: 1439px;
    background-color: #fff;
}

.banner ul {
    box-sizing: border-box;
    margin: 0px auto;
    padding: 29px 0px;
    list-style: none;
    width: 1011px;
}

.banner ul li {
    position: relative;
    width: 126px;
    margin-right: 51px;
    float: left;
    text-align: center;
}

.banner ul li:last-child {
    margin-right: 0px;
}

.banner ul li div {
    width: 126px;
    height: 86px;
}

.banner ul li:nth-child(1) div {
    background: url(./images/image1.png) no-repeat center;
    background-size: contain;
}

.banner ul li:nth-child(2) div {
    background: url(./images/image2.png) no-repeat center;
    background-size: contain;
}

.banner ul li:nth-child(3) div {
    background: url(./images/image3.png) no-repeat center;
    background-size: contain;
}

.banner ul li:nth-child(4) div {
    background: url(./images/image4.png) no-repeat center;
    background-size: contain;
}

.banner ul li:nth-child(5) div {
    background: url(./images/image5.png) no-repeat center;
    background-size: contain;
}

.banner ul li:nth-child(6) div {
    background: url(./images/image6.png) no-repeat center;
    background-size: contain;
}


.banner ul li p {
    margin: 15px 0px 6px;
    font-weight: normal;
    font-size: 12px;
    line-height: 17px;
    color: #000000;
}

.banner ul li h4 {
    font-weight: 500;
    font-size: 12px;
    line-height: 17px;
    color: #FD6821;
}

.banner ul li::after {
    content: '';
    position: absolute;
    right: -26px;
    top: 0px;
    height: 86px;
    width: 1px;
    background: #DFDFDF;
}

.banner ul li:last-child::after {
    content: '';
    position: absolute;
    right: 0px;
    top: 0px;
    height: 0px;
    width: 0px;
    background: #DFDFDF;
}
```

#### 微博头部开发

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>微博实战--head</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <header>
        <div></div>
        <div class="search-box">
            <input type="text" value="大家正在搜：中国队开赛三天已超上届金牌总数">
            <div></div>
        </div>
        
        <main>
            <div class="content">
                 <ul class="clearFix">
                 <li>
                    <div></div>
                    <span>首页</span>
                 </li>
                 <li>
                    <div></div>
                    <span>视频</span>
                 </li>
                 <li>
                    <div></div>
                    <span>发现</span>
                 </li>
                 <li>
                    <div></div>
                    <span>游戏</span>
                 </li>
                 </ul>
            </div>
            <div class="login">
                <ul>
                    <li>注册</li>
                    <li>登录</li>
                </ul>

            </div>
        </main>
           
    </header>

</body>

</html>
```

```css
* {
    margin: 0px;
    padding: 0px;
}
body{
    background: #D0CDCD;
}
header{
position: relative;
width: 1440px;
height: 50px;
background-color: #ffffff;
box-shadow: 0 0 1px 0 #0000004d;
}
header>div{
    position: absolute;
    left: 110px;
    top: 11px;
width: 80px;
height: 27px;
background: url(./images/weibo-header.png) no-repeat center;
background-size: contain;
}
.search-box{
    position: absolute;
    left: 220px;
    top: 11px;
width: 470px;
height: 30px;
}
.search-box>input{
width: 470px;
height: 30px;
color: #808080ff;
background: #f2f2f2ff;
font-size: 12px;
font-weight: 500;
text-align: left;
line-height: 28.6px;
padding-left: 10px;
border: none;
outline:none;
}
.search-box>div{
    position: absolute;
    left: 439px;
    top: 7px;
float: right;
width: 16px;
height: 16.02px;
background:url(./images/search.png) no-repeat center;
background-size: contain;
}
.content{
    position: absolute;
    left: 1007px;
    top: 16px;
    width: 229px;
    height: 17px;
}
.content ul{
    box-sizing: border-box;
    margin: 0 auto;
    list-style: none;
    width: 229px;
}
.content ul li{
    width: 17px;
    margin-right: 44px;
    float: left;
    text-align: center;
}
.content ul li:last-child{
    margin-right: 0px;
}
.content ul li div{
    width: 17px;
    height: 17px;
}
.content ul li:nth-child(1) div{
    background: url(./images/first-page.png) no-repeat center;
    background-size: contain;
}
.content ul li:nth-child(2) div{
    background: url(./images/video.png) no-repeat center;
    background-size: contain;
}
.content ul li:nth-child(3) div{
    background: url(./images/find.png) no-repeat center;
    background-size: contain;
}
.content ul li:nth-child(4) div{
    background: url(./images/game.png) no-repeat center;
    background-size: contain;
}
.content ul li:nth-child(1) span{
display: inline-block;
position: absolute;
left: 22px;
top:3px;
width: 24px;
height: 12px;
color: #000000ff;
font-size: 12px;
font-weight: 400;
text-align: left;
line-height: 12px;
}
.content ul li:nth-child(2) span{
display: inline-block;
position: absolute;
left: 83px;
top:3px;
width: 24px;
height: 12px;
color: #000000ff;
font-size: 12px;
font-weight: 400;
text-align: left;
line-height: 12px;
}
.content ul li:nth-child(3) span{
    display: inline-block;
    position: absolute;
    left: 144px;
    top:3px;
    width: 24px;
    height: 12px;
    color: #000000ff;
    font-size: 12px;
    font-weight: 400;
    text-align: left;
    line-height: 12px;
}
.content ul li:nth-child(4) span{
    display: inline-block;
    position: absolute;
    left: 205px;
    top:3px;
    width: 24px;
    height: 12px;
    color: #000000ff;
    font-size: 12px;
    font-weight: 400;
    text-align: left;
    line-height: 12px;
}
.login{
    position: absolute;
    left:1266px;
    top: 19px;
    width: 69px;
    height: 12px;
}
.login ul{
    box-sizing: border-box;
    margin: 0 auto;
    padding: 19px 0px;
    list-style: none;
    width: 69px;
}
.login ul li{
    width: 24px;
    height: 12px;
    margin-right: 21px;
    float: left;
    text-align: center;
    color: #000000ff;
font-size: 12px;
font-weight: 400;
text-align: left;
line-height: 12px;

}
.login ul li:last-child{
    margin-left: 0px;
}
.login ul li:first-child{
    position: absolute;
    left: 0px;
    top: 0px;
}
.login ul li:last-child{
    position: absolute;
    left: 45px;
    top: 0px;
}
.login ul li::after{
    content: '';
    position: absolute;
    left: 34px;
    width: 1px;
height: 14px;
background: #d9d9d9ff;
}
.login ul li:last-child::after{
    width: 0;
}


```

## css装饰

### css装饰--cursor

#### cursor添加的方法

```html
<p>点击这里了解更多cursor性质</p>
```

```css
p{
    cursor: pointer;
}
```

#### cursor的值

![image-20230603173000247](图片/image-20230603173000247.png)

#### 实例

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
        <li>手机 电话卡</li>
        <li>电视 盒子</li>
        <li>笔记本 平板</li>
        <li>家电 插线板</li>
        <li>出行 穿戴</li>
        <li>智能 路由器</li>
        <li>电源 配件</li>
        <li>健康 儿童</li>
        <li>耳机 音箱</li>
        <li>生活 箱包</li>
    </ul>
</body>

</html>
```

```css
body {
    margin: 0px;
}

ul {
    width: 234px;
    margin: 0;
    padding: 20px 0px;
    list-style: none;
    background-color: #7B8795;
    color: #ffffff;
}

ul>li {
    position: relative;
    height: 42px;
    line-height: 42px;
    padding-left: 30px;
}

ul>li::after {
    content: '';
    position: absolute;
    top: 15px;
    right: 20px;
    width: 12px;
    height: 12px;
    background: url(./images/right-point.png) no-repeat center;
    background-size: contain;
}
ul>li:hover{
    background-color: #FD6821;
    cursor: pointer;
}


```

### CSS装饰--box-shadow/text-shadow

#### box-shadow--盒子阴影

查看阴影的值：https://www.cssmatic.com/box-shadow

设置阴影

```css
div{
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.11);
}
```

#### text-shadow--文字阴影

设置文字阴影

```css
span{
    text-shadow: 0px 0px 10px rgba(0, 0, 0, 0.11);
}
```

#### 实例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>练习</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <div class="box">
        <h3>小米&lt;小爱老师&gt;</h3>
        <p>口袋里的英语外教</p>
        <h4>499元起</h4>
    </div>
</body>

</html>
```

```css
* {
    margin: 0;
    padding: 0;
}

.box {
    box-sizing: border-box;
    width: 200px;
    height: 256px;
    background: #ffffff;
    padding-top: 22px;
    text-align: center;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.11);
}

.box::before {
    content: '';
    display: block;
    width: 130px;
    height: 130px;
    margin: 0px auto 16px;
    background: url(./images/phone.jpg) no-repeat center;
    background-size: contain;
}

.box h3 {
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 17px;
    color: #000000;
}

.box p {
    margin-top: 4px;
    margin-bottom: 8px;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 17px;
    color: #A8A8A8;
}

.box h4 {
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 17px;
    color: #FD6821;
}
```

### 微博个人banner开发

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>微博实战--banner</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <header>
        <div class="box">
            <div class="head-icon"></div>
            <div class="v"></div>
            <p>我是娜扎</p>
            <div class="sex"></div>
            <div class="level"></div>
            <span>演员，代表作《择天记》</span>
            <button class="add">
                <div></div>
                <span>关注</span>
            </button>
            <button class="triangle">
                <div></div>
            </button>
            <button class="private">
                <span>私信</span>
            </button>
            <button class="list">
                <div></div>
            </button>
        </div>
        <div class="list-box">
            <ul>
                <li>她的主页</li>
                <li>她的相册</li>
            </ul>
        </div>
    </header>

</body>

</html>
```

```css
* {
    margin: 0;
    padding: 0;
}
header{
    position: relative;
    width: 920px;
    height: 340px;
}
.box{
    position: absolute;
    width: 920px;
    height: 300px;
    background: url(./images/banner-bg.png) no-repeat center;
    background-size: contain;
}
.box>.head-icon{
    position: absolute;
    left: 407.2px;
    top: 30px;
    width: 107.8px;
    height: 110px;
    border-radius: 50%;
    background: url(./images/banner-head-icon.png) no-repeat center;
    background-size: contain;
}
.v{
    position: absolute;
    left: 487px;
    top: 116px;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: url(./images/v-logo.png) no-repeat center;
    background-size: contain;
}
.box>p{
    position: absolute;
    left: 393px;
    top: 150px;
width: 88px;
height: 29px;
opacity: 1;
color: #ffffffff;
font-size: 22px;
font-weight: 500;
text-align: center;
line-height: 28.6px;
}

.box>.sex{
    position: absolute;
    left: 489px;
    top:159px;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background: url(./images/sex-icon.png) no-repeat center;
    background-size: contain;
}
.level{
    position: absolute;
    left: 513px;
    top: 160px;
    width: 16px;
    height: 15.06px;
    border-radius: 50%;
    background: url(./images/leval-icon.png) no-repeat center;
    background-size: contain;
}
.box>span{
    position: absolute;
    left: 393px;
    top: 184px;
    width: 132px;
height: 20px;
opacity: 1;
color: #ffffffff;
font-size: 12px;
font-weight: 500;
text-align: left;
line-height: 20px;
}
.add{
    position: absolute;
    left: 323px;
    top: 223px;
    width: 100px;
height: 32px;
border-radius: 2px;
background: linear-gradient(180.25deg, #fa823cff 0%, #f55f10ff 100%);
border: none;
}
.add>div{
    position: absolute;
    left: 27.44px;
    top: 10.67px;
    width: 11.11px;
height: 10.68px;
background: url(./images/add-icon.png) no-repeat center;
background-size: contain;
}
.add>span{
    position: absolute;
    left: 42.33px;
    top: 6.33px;
    width: 31.11px;
height: 21.33px;
opacity: 1;
color: #ffffffff;
font-size: 14px;
font-weight: 500;
text-align: center;
line-height: 20px;
}
.triangle{
    position: absolute;
    left: 428px;
    top: 223px;
width: 20px;
height: 32px;
border-radius: 2px;
background: linear-gradient(180.25deg, #fa823cff 0%, #f55f10ff 100%);
border: none;
}
.triangle>div{
position: absolute;
left:7px;
bottom: 14px;
width: 6.93px;
height: 4px;
background:url(./images/triangle-icon.png) no-repeat center;
background-size: contain;
}
.private{
    position: absolute;
    left: 460px;
    top: 223px;
    width: 100px;
height: 32px;
border-radius: 2px;
background: #70757fff;
border: none;
}
.private>span{
    position: absolute;
    left: 34px;
    top: 6.33px;
    width: 31.11px;
height: 21.33px;
color: #ffffffff;
font-size: 14px;
font-weight: 500;
text-align: center;
line-height: 20px;
}
.box>.list{
    position: absolute;
    left: 568px;
    top:223px;
    width: 30px;
height: 32px;
border-radius: 2px;
background: #70757fff;
border: none;
}
.box .list>div{
    position: absolute;
    left: 8px;
    bottom: 11px;
    width: 14px;
height: 11px;
background: url(./images/list-icon.png) no-repeat center;
background-size: contain;
}
.list-box{
    position: absolute;
    top: 300px;
    width: 920px;
    height: 40px;  
}
.list-box ul{
    box-sizing: border-box;
    list-style: none;
    box-sizing: border-box;
    margin: 0 auto;
    padding: 12px 294px 14px 294px;
    width: 920px;
}
.list-box ul li{
    position: relative;
    width: 56px;
    height: 14px;
    margin-right: 220px;
    float: left;
    text-align: center;
}
.list-box ul li:first-child{
color: #000000ff;
font-size: 14px;
font-weight: 700;
text-align: center;
line-height: 14px;
}
.list-box ul li:last-child{
color: #000000ff;
font-size: 14px;
font-weight: 400;
text-align: center;
line-height: 14px;
margin-right: 0;
}
.list-box ul li:first-child::after{
    content: '';
    position: absolute;
    left: -7px;
    top: 26px;
    width: 70px;
height: 2px;
opacity: 1;
background: #f7691dff;
}

```

