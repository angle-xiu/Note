# system
[toc]
## 环境配置

## 问题处理

## 数据处理
+ 可以通过线上数据转格式工具进行转换成json格式的文件（数据量较小或者用于展示时），或者通过Python进行转换。（适合后期功能完善，需调用数据库时）
## 关于使用库
+ 1.确定自己所需的库以及所需的依赖。
+ 2.分清不同依赖的版本，参考文档的要求进行下载。
+ 3.引入库时注意顺序，根据依赖关系导入，例如在引入bootstrap.min.js时，需要
先引入jQuery.min.js
## bootstrap + jquey入门
+ [Bootstrapv3官方文档](https://v3.bootcss.com/)    一般情况使用这个版本就可以。更高版本部分情况下会出现兼容问题。
+ [Jquery官方文档](https://www.jquery123.com/)    查看对应版本的文档。部分API可能更新或者废弃。
### bootstrap `基本内容及简述`
+ 1.项目起步需要的配置
+ 下载依赖包
  - https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css

  - http://cdn.static.runoob.com/libs/jquery/2.1.1/jquery.min.js

  - https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js

  - https://v3.bootcss.com/getting-started/

进入下载用于生产环境的 Bootstrap 包

+ 引入 css 和 js 文件
<link rel="stylesheet" type="text/css" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css">
<script type="text/javascript" src="http://cdn.static.runoob.com/libs/jquery/2.1.1/jquery.min.js"></script>
<script type="text/javascript" src=" https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js">   </script>
+ 定义根据设备的大小调整页面的显示宽度
<meta name="viewport" content="width=device-width,initial-scale=1">
+ 2.Bootstrap 栅格化（核心布局功能）
    栅格系统的重要性，它能够让你的布局在各个浏览器中都能适应。以下栅格的用法。

栅格布局通常有四个样式：

col-lg-* ：大型设备
col-md-*：中型设备
col-sm-*：小型设备
col-xs-*：极小型设备
如果想要使用栅格系统，必须按照以下方式定义：

所有的栅格一定要建立在容器之中（“container”或者“container-fluid”）
每一行都具备 12 栅格划分，所以在使用栅格的组件里面使用“.row”样式
每一列都是行的子元素，所有内容应该放到列的内部
每一列都可以使用 col-lg-*，col-md-*，col-sm-*，col-xs-* 样式
为了更好的理解，下面实现一个简单的栅格操作：
```
     <div class="container">
          <div class="row">
              <div class="col-lg-4 col-md-4">1</div>
              <div class="col-lg-4 col-md-4">2</div>
              <div class="col-lg-4 col-md-4">3</div>
          </div>
          <div class="row">
              <div class="col-md-6">栅格1</div>
              <div class="col-md-6">栅格2</div>
          </div>
      </div>
```
在此基础上，我们再来介绍一下使用列偏移\嵌套列\列排序：

列偏移：.col-lg/md/sm/xs-offset-*（通过使用 * 选择器为当前元素增加了左侧的边距）
eg:将 .col-md-4 元素向右侧偏移4个列（column）的宽度：
```

           <div class="row">
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-4 col-md-offset-4">.col-md-4 .col-md-offset-4</div>
          </div>
```
嵌套列：使用内置的栅格系统将内容再次嵌套
```
      eg:<div class="row">
              <div class="col-md-12">
                <div class="row">
                  <div class="col-md-6">栅格1</div>
                  <div class="col-md-6">栅格2</div>
                </div>
              </div>
          </div>
```
列排序：使用 .col-md-push-* 和 .col-md-pull-* 类就可以很容易的改变列的顺序
```
       <div class="row">
            <div class="col-md-9 col-md-push-3">.col-md-9 .col-md-push-3</div>
            <div class="col-md-3 col-md-pull-9">.col-md-3 .col-md-pull-9</div>
        </div>
```
+ 3.Bootstrap各个组件的介绍与使用
面板（Panels）
面板：需要向 <div> 元素添加 class .panel 和 class .panel-default 即可，也可设置带有色彩的面板，只需将 panel-default 替换（panel-primary、panel-success、panel-info、panel-warning、panel-danger）即可
面板标题容器：（向面板添加标题容器 .panel-heading）
面板标题：用带有 .panel-title class 的 <h1>-<h6> 来添加预定义样式的标题
面板脚注： 添加 class.panel-footer
如下面的实例所示：

```
    <div class="col-lg-4 col-md-4">
          <div class="panel panel-default">
               <div class="panel-heading">
                      <h3 class="panel-title">
                       带有 title 的面板标题
                      </h3>
              </div>
              <div class="panel-body">
                    这是一个基本的面板
              </div>
              <div class="panel-footer">面板脚注</div>
         </div>
   </div>
```
效果： 
![](http://images.gitbook.cn/2db0f570-5432-11e8-8a20-b1c15bb5d898)

下拉菜单（dropdown）
用 class.dropdown 来修饰 div
用 class.dropdown-menul 来修饰下拉菜单的内容
button 的 id 值一定要与下拉菜单内容中 aria-labelledby 的值相对应
button 一定要引用 data-toggle="dropdown"，代码可下拉
如下面的实例所示：

```
      <div class="dropdown">
              <button class="btn btn-default" type="button" id="dropdownMenu1" data-toggle="dropdown" >
                      Dropdown
                    <span class="caret"></span>
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdownMenu1">
              <li><a href="#">Action</a></li>
            </ul>
   </div>
```
效果：
![图](http://images.gitbook.cn/550d40b0-5432-11e8-8a20-b1c15bb5d898)

按钮组（btn-group）
用 .btn-group 来修饰 div
对按钮组大小设置（btn-group-xs、btn-group-md、btn-group-lg）
垂直按钮组只要添加 class.btn-group-vertical 样式即可
对齐按钮组只要将 .btn 按钮放置在 class.btn-group-justified 样式里即可
对按钮颜色设置 （btn-default、btn-primary、btn-success、btn-info、btn-warning、btn-danger）
对按钮大小设置 （btn-lg、btn-md、btn-sm、btn-xs）
如下面的实例所示（结合上面的下拉菜单为按钮式下拉菜单）：

```
   <div class="col-lg-4 col-md-4">
           <div class="btn-group btn-group-lg btn-group-vertical" role="group" aria-label="...">
                    <button type="button" class="btn btn-info ">Left</button>
                    <button type="button" class="btn btn-danger">Middle</button>
                    <button type="button" class="btn btn-default" id="dropdownMenu1" data-toggle="dropdown">Right</button>
                    <ul class="dropdown-menu" aria-labelledby="dropdownMenu1">
                      <li><a href="#">Action</a></li>
                    </ul>
           </div>
   </div>
```
效果
![1](http://images.gitbook.cn/6f0f45d0-5432-11e8-8a20-b1c15bb5d898)

输入框组（input-group）
通过在文本输入框 <input> 前面、后面或是两边加上文字或按钮，可以实现对表单控件的扩展。
为 .input-group 赋予 .input-group-addon 或 .input-group-btn 类，可以给 .form-control 的前面或后面添加额外的元素。
基本实例：

在前面增加元素：
```
     <div class="input-group">
                    <span class="input-group-addon" id="basic-addon1">@</span>
                    <input type="text" class="form-control" placeholder="Username" aria-describedby="basic-addon1">
     </div>
```
在后面增加元素：
```
   <div class="input-group">
                    <input type="text" class="form-control" placeholder="Recipient's username" aria-describedby="basic-addon2">
                    <span class="input-group-addon" id="basic-addon2">@example.com</span>
  </div>
```
在前后增加元素：
```
  <div class="input-group">
                    <span class="input-group-addon">$</span>
                    <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
                    <span class="input-group-addon">.00</span>
  </div>
```
效果：
![1](http://images.gitbook.cn/7b6d78b0-5432-11e8-8a20-b1c15bb5d898)

导航条（navbar）
用 navbar navbar-default 来修饰 div 或者 nav
如果导航条上存在 form，那么给 form 表单加上 navbar-form
按钮 navbar-btn
文本 navbar-text
链接 navbar-link
固定在顶部 navbar-fixed-top 或者底部 navbar-fixed-bottom
navbar 中可包裹一个 container|container-fluid
反色 navbar-inverse
基本实例：
```
      <form class="navbar-form">
            <nav class="navbar navbar-default navbar-fixed-top navbar-inverse">
                <div class="pull=left navbar-text">名字</div>
                <button class="navbar-btn">名字</button>
                <a class="pull-right navbar-link">www.baidu.com</a>
           </nav>
   </form> 
```
效果:
![1](http://images.gitbook.cn/0ab17f30-5433-11e8-8a20-b1c15bb5d898)

列表（list-group）
.list-group 修饰 <ul>
模态框（modal）
模态框经过了优化，更加灵活，以弹出对话框的形式出现，减少了页面的跳转，更加方便简洁
模态框由头部（modal-title），内容（modal-body）及操作区域（modal-footer）组成
对button设置 data-toggle="modal" data-target="#myModal"
对modal 设置 id 和 data-target 的值对应
data-dismiss="modal" 是对模态框设置关闭
动态实例如下：

```
      <button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#myModal">
                  Launch demo modal
     </button>
    <!-- Modal -->
     <div class="modal fade" id="myModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">
       <div class="modal-dialog" role="document">
         <div class="modal-content">
           <div class="modal-header">
             <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
             <h4 class="modal-title" id="myModalLabel">Modal title</h4>
           </div>
           <div class="modal-body">
             ...
           </div>
           <div class="modal-footer">
             <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
             <button type="button" class="btn btn-primary">保存</button>
           </div>
         </div>
       </div>
     </div>
```
效果：

![1](http://images.gitbook.cn/9a4807f0-5432-11e8-8a20-b1c15bb5d898)
标签页（tab）
tab 页的出现，让我们减少了很多空间在同一区域通过不同按钮的切换便可实现不同的内容
按钮中 a 标签 href 的指向应该是它相对应内容的 id
基本实例如下：
```
<div>
              <!-- Nav tabs -->
               <ul class="nav nav-tabs" role="tablist">
                 <li role="presentation" class="active"><a href="#home" aria-controls="home" role="tab" data-toggle="tab">Home</a></li>
                 <li role="presentation"><a href="#profile" aria-controls="profile" role="tab" data-toggle="tab">Profile</a></li>

               </ul>
             <!-- Tab panes -->
              <div class="tab-content">
                <div role="tabpanel" class="tab-pane active" id="home">1</div>
                <div role="tabpanel" class="tab-pane" id="profile">2</div>
              </div>
</div>
```
效果： 
![1](http://images.gitbook.cn/a2fd08f0-5432-11e8-8a20-b1c15bb5d898)

弹出框（Popover）
弹出框适用于信息的提示
data-content里的内容可是是一句话，可以是一些操作，本章我们只介绍如何使用弹出框，对过于复杂的操作不做阐述
弹出框必须通过js启动
data-placement是指设置弹出框的方向（top，left，right，bottom）
基本实例：

html代码：
```
     <button id="example" type="button" class="btn btn-default" data-container="body" data-toggle="popover" data-placement="right" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
  Popover on 右侧
</button>
```
js代码：
```
   <script type="text/javascript">
        $('#example').popover()
   </script>
```
效果：

![1](http://images.gitbook.cn/b149ec70-5432-11e8-8a20-b1c15bb5d898)
工具提示（tooltip）
主要用来提示目前元素是干什么用的
data-placement 设置提示信息的方向（top，right，bottom，left）
启动提示信息需要 js 代码完成
基本实例：

html代码：
```
    <button type="button" class="btn btn-default" data-toggle="tooltip" data-placement="bottom" title="Tooltip on bottom">Tooltip on bottom</button>
```
js代码：
```
    $('[data-toggle="tooltip"]').tooltip()
```
警告框（alert）
用来提示发生了什么
不同的颜色代码不同的含义（alert-success、alert-info、alert-warning、alert-danger），需要根据需求来分析适合用那个色系来提示警告信息
可关闭只需添加data-dismiss="alert" aria-label="Close"
基本实例：

```
  <div class="alert alert-success" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
            Better check yourself, you're not looking too good
  </div>
  <div class="alert alert-info" role="alert">...</div>
 <div class="alert alert-warning" role="alert">...</div>
  <div class="alert alert-danger" role="alert">...</div>
```
效果： 

![1](http://images.gitbook.cn/be510980-5432-11e8-8a20-b1c15bb5d898)
表格（table）
表格分为多种类型，包含基本表格、条纹状表格（.table-striped）、带边框的表格（.table-bordered）、紧缩表格（.table-condensed）
鼠标悬停表格上（.table-hover）
表格每一行都可设置不同的样式，可需要加上样式（.success、.info、.warning、.danger）
鼠标悬停在行或单元格上时所设置的颜色（.active）
基本实例
```

        <table class="table table-striped table-hover">
               <thead>
                 <tr>  
                   <th>1</th>
                   <th>2</th>
                 </tr>
               </thead>
              <tbody>
                <tr>
                  <td class="active">11</td>
                  <td class="success">22</td>
                </tr>
              </tbody>
     </table>
```
效果：
![1](http://images.gitbook.cn/c8456850-5432-11e8-8a20-b1c15bb5d898)

表单（form-group）
基本实例：

```
    <form>
                  <div class="form-group">
                    <label for="exampleInputEmail1">Email address</label>
                    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
                  </div>
                  <div class="form-group">
                    <label for="exampleInputPassword1">Password</label>
                    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
                  </div>
                  <div class="form-group">
                    <label for="exampleInputFile">File input</label>
                    <input type="file" id="exampleInputFile">
                    <p class="help-block">Example block-level help text here.</p>
                  </div>
                  <div class="checkbox">
                    <label>
                      <input type="checkbox"> Check me out
                    </label>
                  </div>
                  <button type="submit" class="btn btn-default">Submit</button>
                </form>
```
效果： 
![1](http://images.gitbook.cn/d1bc59c0-5432-11e8-8a20-b1c15bb5d898)
4. 字体图标的使用
下载所需用的字体图标
修改 bootstrap.min.css 里图标的路径
满足上面两点，便可使用字体图标，如果想要改变字体图标的颜色和大小，新增class便可，记住，字体图标的大小是通过 font-size 改变的
基本实例：
```
    <span class="glyphicon glyphicon-user"></span>
```
效果： 
![1](http://images.gitbook.cn/d8e7d490-5432-11e8-8a20-b1c15bb5d898)


## 调试技巧
### 文件未加载（样式或js效果不出现，首先排查文件是否加载成功）
+ 按f12打开控制台查看点击console是否出现报错，一般都是路径问题。
    ![1](https://pic.liesio.com/2020/10/16/dff8b68b964e4.png)
 
### 调试样式（css）
+ 查看元素对应的样式
    - 1、打开调试工具，点击调试工具左上角的检查元素按钮或者快捷键（Ctrl/Cmd + Shift + C）
![1](https://img-blog.csdnimg.cn/20181221112202925.png)
    - 2、在页面选中需要查看的元素，被检查的元素在DOM树中以蓝色背景突出显示，样式在右侧 styles 选项卡区域内。
![1](https://img-blog.csdnimg.cn/20181221112407116.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)

+ 查看外部样式表
    - 1、在 styles 选项卡中，单击CSS规则旁边的链接以打开定义规则的外部样式表。可以查看样式的源文件。
![1](https://img-blog.csdnimg.cn/2018122114254266.png)

+ 仅查看实际应用于元素的CSS
    - 1、styles 选项卡中会显示适用于元素的所有规则，包括已被覆盖的声明，如果对覆盖的声明不感兴趣，可以点击与 styles 相邻的 computed 选项卡，仅查看实际应用于元素的CSS规则。

    - 2、其中继承的属性是不透明的。选中 Show All 复选框可以查看所有继承的值。

    - 3、注意属性的显示是按照字母顺序排列的。

    - 4、Filter 过滤器可以按照查询规则搜索符合规则的样式。

    - 5、当鼠标悬浮在某一行属性上时，会出现一个圆形箭头按钮，点击可以跳转到styles 选项卡所对应的样式处。
![1](https://img-blog.csdnimg.cn/20181221144058729.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)
+ 查看元素伪状态
    - 1、在 styles 选项卡中点击 :hov 。以 :hover 为例，选中 :hover 复选框，如果
被检查的元素添加了 :hover 样式，在样式列表中就会显示此条样式。并且页面效果不用鼠标悬浮也会触发显示效果。
![1](https://img-blog.csdnimg.cn/20181221121731937.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)

+ 添加或更改CSS样式
添加内联样式
    - 1、相当于向HTML的 style 属性的添加属性值。点击 element.style 顶部附近区域，输入新添加的样式属性名，按 Tab 键，再输入样式属性值，并按 Enter 键。这样就添加了一条内联样式。
![1](https://img-blog.csdnimg.cn/2018122114543188.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)
    - 2、查看效果：


+ 向已有样式规则添加声明
1、单击要添加声明的样式规则的括号之间。出现光标，输入属性名，按 tab 键，输入属性值，回车。

修改已有样式规则的声明
1、在需要更改的原有样式上双击，修改样式规则，并按 Enter 键。
![1](https://img-blog.csdnimg.cn/2018122111491540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)
给元素添加CSS类
1、在 styles 选项卡中点击 .cls 。会显示一个 Add new class 的输入框，你可以输入你想要添加的类名，然后按 Enter 键。
![1](https://img-blog.csdnimg.cn/20181221115431861.png)

2、点击 title 前方的复选框可以来回切换样式。

+ 添加新样式规则
1、单击 styles 选项卡右上角的加号1➕，DevTools会在 element.style 规则下插入一条新规则。

2、如果想在特定位置添加新样式规则，可以鼠标悬浮在插入规则的上一个样式规则处，此时会在右下角出现三个点更多操作的符号，x悬浮上去就会出现加号2➕，点击加号2就会在此条样式的后面新增一条样式规则。

3、这里的更多操作还有其他一些功能，从左往右依次是 文字阴影、盒子阴影、文字颜色、背景颜色。
![1](https://img-blog.csdnimg.cn/20181221155256850.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)

+ 切换样式声明
1、点击样式声明前的复选框就可以切换样式声明
![1](https://img-blog.csdnimg.cn/20181221160002971.png)

+ 更改元素尺寸
1、在 styles 选项卡的框模型图中，将鼠标悬浮在需要编辑的区域，双击，填入需要修改的数值，回车。盒模型的默认单位为像素，输入百分比也会转成像素值。
![1](https://img-blog.csdnimg.cn/20181221140521680.png)

使用键盘快捷键更改声明值
编辑声明的值时，可以使用以下键盘快捷键将值递增固定量：

Up 将值更改为1，如果当前值介于-1和1之间，则更改0.1。
Option+ Up（Mac）或Alt+ Up （Windows，Linux）增加0.1。
Shift+ Up增加10。
Shift+ Command+ Up（Mac）或 Shift+ Page Up（Windows，Linux）将值增加100。
减量也有效。只需将Up上面提到的每个实例替换为Down。

+ 使用Coverage选项卡查看已使用和未使用的CSS
1、按下Command+ Shift+ P（Mac）或 Control+ Shift+ P（Windows，Linux，Chrome OS），而DevTools则处于焦点以打开命令菜单。
2、开始输入coverage并选择Show Coverage。将显示 coverage 选项卡。
![1](https://img-blog.csdnimg.cn/20181221152009109.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)
3、单击“to reload and start capturing coverage” 开始检测覆盖范围并重新加载页面。页面重新加载，Coverage选项卡提供浏览器加载的每个文件使用多少CSS（和JavaScript）的概述。绿色代表使用CSS。红色表示未使用的CSS。
![1](https://img-blog.csdnimg.cn/20181221152442477.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)
4、单击一个CSS文件，查看它使用的CSS的逐行细分。
![1](https://img-blog.csdnimg.cn/20181221152646375.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)

+ 拾色器的使用
面板说明
以下是拾色器的每个UI元素的说明：
1、阴影。
2、吸管。
3、复制到剪贴板。将显示值复制到剪贴板。
4、显示价值。RGBA，HSLA或Hex的颜色表示。
5、调色板。单击其中一个方块可将颜色更改为该方块。
6、色相。
7、透明度。
8、显示值切换器。在当前颜色的RGBA，HSLA和Hex表示之间切换。
9、调色板切换器。在“ 材质设计”调板，自定义调色板或页面调色板之间切换。DevTools根据它在样式表中找到的颜色生成页面调色板。
![1](https://img-blog.csdnimg.cn/2018122116045340.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3VzZXJrYW5n,size_16,color_FFFFFF,t_70)

使用吸管从页面上取样
打开拾色器时，默认情况下吸管 滴管处于打开状态。要将所选颜色更改为页面上的其他颜色：
1、将鼠标悬停在视口中的目标颜色上。
2、点击确认。