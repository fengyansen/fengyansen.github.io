# 前端HTML

参考文档：MDN标题标签文档

## audio标签

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
  </head>
  <body>
    <audio controls="controls" src="https://document.youkeda.com/P3-1-HTML-CSS/1.2/nocturne.mp3" muted>
    您的浏览器不支持audio标签
    </audio>
  </body>
</html>

```

## 进度条标签

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
  </head>
  <body>
    <progress id="file" max="100" value="50"> 50% </progress>
  </body>
</html>

```

## 段落和图片标签

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>图片</title>
  </head>
  <body>
    <h1>Beautiful World</h1>
    <p>
      God adds beautiful objects and images on planet earth, such as sunrise,
      sunset, rainbows, snows on mountain tops, and many others. Don't spare your
      compliment of our beautiful world.
    </p>

    <h2>Islands</h2>
    <h3>Maldives</h3>
    <p>
      Unrivalled luxury, stunning white-sand beaches and an amazing underwater
      world make Maldives an obvious choice for a true holiday of a lifetime.
    </p>
    <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.3/1-3-island-2.jpg" alt="">
    <h3>Crete Island</h3>
    <p>
      The largest island in <strong>Greece</strong>. Crete is a feast for the
      senses: wild natural beauty and thousands of years of culture, history and
      exquisite cuisine.
    </p>
    <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.3/1-3-island-1.jpg">
    <p>
      Whether your visit is for relaxation or to explore and discover the many
      well known and countless hidden treasures of <strong>Crete</strong>, you
      will not be disappointed by the diversity of the landscape – the rugged
      mountains, the endless beaches and the turquoise seas, the many cities,
      towns and villages, and stunning countryside.
    </p>

    <h2>Mountains</h2>
    <h3>Matterhorn, Swiss-Italian Border</h3>
    <p>
      It may not be the height peak in <strong>The Alps</strong>. But, there are
      no other peaks in the Alps or in the rest of the world is as beautiful as
      Matterhorn. It’s truly a magical attraction. This pyramidal shaped mountain
      situated on Swiss -Italian border. Rising 4478 meters above sea level it is
      one of the highest peaks Switzerland. The faces of Matterhorn are steep. So,
      the climbing could be difficult.
    </p>
    <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.3/1-3-mountain-1.jpg">
    <h3>Kirkjufell</h3>
    <p>
      Standing tall above the small fishing town of
      <strong>Grundarfjörður</strong>, <strong>Kirkjufell</strong> is the most
      photographed mountain in <strong>Iceland</strong>, one of the top 10 most
      beautiful mountains in the world, and yet most recognized as being “Arrow
      Head Mountain” on Game of Thrones.
    </p>
    <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.3/1-3-mountain-2.jpg">
    <p>
      Most amazing places in the world are worth adding to your travel bucket
      list. Pick up your backpack and go.
    </p>
  </body>
</html>

```

## 链接标签

target属性的值：

_self：在当前页面打开

_blank：在新页面打开

_parent :会在父窗口或者包含来超链接引用的框架的框架集中打开链接

_top:会清除所有被包含的框架，并打开链接。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
  </head>
  <body>
    <a href="https://style.youkeda.com/pages/BeautifulWorld.html" target="_parent">原文链接</a>
  </body>
</html>

```

## 列表标签

### 无序

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>改错题</title>
  </head>
  <body>
    <ul>
      <li>标注今天的青蛙123</li>
      <li>每天结束填写回顾和反思</li>
      <li>计划第二天的青蛙</li>
    </ul>
  </body>
</html>

```

### 有序

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>编程题</title>
  </head>
  <body>
    <ol>
    <li>送奶奶去体检</li>
    <li>完成工作画稿</li>
    <li>给今天生日的孩子买蛋糕</li>
    <li>看完《滑动解锁》的最后一部分</li>
    </ol>
  </body>
</html>
```

## form标签

### 单行文本输入框

#### 文本框基本格式

```html
<!-- action=""则表单信息将提交到当前页面 -->
<form action="">
  <input type="text" />
</form>
```

#### 占位文本、

_提示用户需要输入什么_

```
<input type="text" placeholder="昵称" />
```

#### 输入框名字

```html
<input type="text" placeholder="昵称" name="nick" />
```

#### 输入框的值

```html
<input type="text" placeholder="昵称" name="nick" value="小明" />
```

#### 不可修改的输入框“readonly”和“disabled”

```html
<input type="text" placeholder="昵称" name="nick" value="小明" readonly />
```

#### 实例：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
  </head>
  <body>
    <form action="https://www.youkeda.com/">
      <input type="text" placeholder="这是个只能看不能改的输入框" name="unmodifiable" readonly>
      
    </form>
  </body>
</html>

```

### 多行文本输入框

_rows_：行数（高度）

_cols_：文本域的可视宽度

```html
<!-- name属性表示表单元素的名称，placeholder属性表示表单元素的占位文本 -->
<textarea
  name="sign"
  rows="5"
  cols="30"
  placeholder="请输入个性签名"
></textarea>
```

#### 实例：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>改错题</title>
  </head>
  <body>
    <form action="https://www.youkeda.com/">
      <textarea name="evaluate" placeholder="请输入自我评价"></textarea>
    </form>
  </body>
</html>

```



### 密码输入框

用户输入的内容将会以**黑圆点**的形式显示

<u>只需将type标签属性改成password</u>

```html
<!-- type属性表示表单元素的类型，name属性表示表单元素的名称，placeholder属性表示表单元素的占位文本 -->
<input type="password" name="password" placeholder="密码" />
```

### 单选框和复选框

#### 单选框

性别单选

<u>只是把type的属性改成了radio</u>

同一道单选题的每个单选按钮，应该拥有相同的name属性值，用value=“male”表示男性，用value=“female”表示女性，这两个单词是表单数据提交时提交的内容。如果要展示选项的内容，直接在**input**后面添加。

##### 范围小，只能点击圆点

```html
<input type="radio" name="gender" value="male" />男
<input type="radio" name="gender" value="female" />女
```

##### 范围大还可以点击内容

```html
<!--第一种写法：单选框和标签配合使用-->
<label> <input type="radio" name="gender" value="male" />男 </label>
<label> <input type="radio" name="gender" value="female" />女 </label>

<!--第二种写法：增加属性id=“male”，给label也加了一个属性for=“male”，产生一一对应的关系-->
<input id="male" type="radio" name="gender" value="male" />
<label for="male">男</label>
<input id="female" type="radio" name="gender" value="female" />
<label for="female">女</label>
```

##### 实例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>编程题</title>
</head>
<body>
  <form action="https://www.youkeda.com/">
    <input id="A" type="radio" name="form" value="A" />
    <label for="A">A、form标签是块状标签</label>
    <br>
    <input id="B" type="radio" name="form" value="B" />
    <label for="B">B、form标签内可以写输入框之类的表单控件</label>
    <br>
    <input id="C" type="radio" name="form" value="C" />
    <label for="C">C、form标签可嵌套在form标签内</label>
    <br>
    <input id="D" type="radio" name="form" value="D" >
    <label for="D">D、表单中的内容可以被提交到action属性定义的地址中</label>
  </form>
</body>
</html>
```



#### 兴趣多选框

type的类型是**checkbox**

```html
<label> <input type="checkbox" name="interest" value="coding" />编程 </label>
<label> <input type="checkbox" name="interest" value="other" />其他 </label>
```

##### 实例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>编程题</title>
</head>
<body>
  <form action="https://www.youkeda.com/">
    <label><input type="checkbox" name="a" value="agree">我已阅读并同意相关服务条款和隐私政策</label>

  </form>
</body>
</html>

```

### 选项菜单

#### 单选选项菜单

对于职业的选择，我们给用户提供了很多选项：公司职员、自由职业者、学生、其它，实际情况可能会产生更多的选项。因为选项有点多，所以用到新的标签选项菜单



```html
<!--每个选项用<option>标签表示，一组选项用<select>包裹-->
<select name="career">
  <option value="default">请选择职业</option>
  <option value="staff">公司职员</option>
  <option value="freelancer">自由职业者</option>
  <option value="student">学生</option>
  <option value="other">其他</option>
</select>
```

#### 多选选项菜单

只需给**<select>**标签添加**multiple**属性，然后按住**ctrl**并单击选项来选中多个选项啦

```html
<select name="career" multiple>
  <option value="default">请选择职业</option>
  <option value="staff">公司职员</option>
  <option value="freelancer">自由职业者</option>
  <option value="student">学生</option>
  <option value="other">其他</option>
</select>
```

### 按钮

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
  </head>
  <body>
    <!--图片地址：https://document.youkeda.com/P3-1-HTML-CSS/1.3/15.png-->
      //跳转链接
    <form action="https://document.youkeda.com/P3-1-HTML-CSS/1.3/15.png">
      <button type="submit">提交</button>
    </form>
  </body>
</html>
```

#### input标签的基本属性类型

![image-20230522175349100](C:\Users\18459\AppData\Roaming\Typora\typora-user-images\image-20230522175349100.png)

# 大作业

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>编程题</title>
    <link rel="stylesheet" href="./index.css">
  </head>
  <body>
    <form action="https://www.youkeda.com/">
      <input type="text" name="name" placeholder="姓名">
      <br>
      <input type="number" name="mobile" placeholder="手机号">
      <br>
      <input type="password" name="password" placeholder="密码">
      <br>
      <input type="checkbox" name="choice" value="agreement" id="agreement">
      <label for="agreement">已阅读并同意使用条款以及非活跃号处理规范</label>
      <br>
      <button type="submit">立即注册</button>
    </form>
  </body>
</html>

```

