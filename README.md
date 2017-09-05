# 记录与html5和css3的知识（移动端） #
# CSS权重 #
- CSS权重指的是样式的优先级，有两条或多条样式作用于一个元素，权重高的那条样式对元素起作用,权重相同的，后写的样式会覆盖前面写的样式。

## 权重的等级（css写的好的时候就不用该部分了） ##

- 可以把样式的应用方式分为几个等级，按照等级来计算权重

1. !important，加在样式属性值后，权重值为 10000
2. 内联样式，如：style=””，权重值为1000
3. ID选择器，如：#content，权重值为100
4. 类，伪类和属性选择器，如： content、:hover 权重值为10
5. 标签选择器和伪元素选择器，如：div、p、:before 权重值为1
6. 通用选择器（*）、子选择器（>）、相邻选择器（+）、同胞选择器（~）、权重值为0

# CSS3新增选择器 #
1. E:nth-child(n)：匹配元素类型为E且是父元素的第n个子元素

# CSS3圆角、阴影、rgba #
## CSS3圆角 ##

- 设置某一个角的圆角，比如设置左上角的圆角：

`border-top-left-radius:30px 60px;`

- 同时分别设置四个角： `border-radius:30px 60px 120px 150px;`

- 设置四个圆角相同：

`border-radius:50%;`

## CSS3阴影 ##
```html
box-shadow：h-shadow v-shadow blur spread color inset;
```
- 分别设置阴影：水平偏移 垂直偏移 羽化大小 扩展大小 颜色 是否内阴影
```html
<style type="text/css">
    .box{
        width:200px;
        height:50px;
        background-color:gold;
        /* box-shadow:10px 10px 5px 2px pink inset; */
        box-shadow:10px 10px 5px 2px pink;
    }
</style>
......
<div class="box"></div>

<!-- 给盒子加上了粉红色的阴影 -->
```

## rgba（新的颜色值表示法）##

1. 盒子透明度表示法：opacity:0.1;filter:alpha(opacity=10)（兼容IE）;
2. rgba(0,0,0,0.1) 前三个数值表示颜色，第四个数值表示颜色的透明度

# CSS3 transition动画（动态的效果） #

1. transition-property 设置过渡的属性，比如：width height background-color
2. transition-duration 设置过渡的时间，比如：1s 500ms
3. transition-timing-function 设置过渡的运动方式

- linear 匀速
- ease 开始和结束慢速
- ease-in 开始是慢速
- ease-out 结束时慢速
- ease-in-out 开始和结束时慢速
- cubic-bezier(n,n,n,n)
  - 比如：cubic-bezier(0.845, -0.375, 0.215, 1.335)
  - 曲线设置网站：https://matthewlein.com/ceaser/
4. transition-delay 设置动画的延迟
5. transition: property duration timing-function delay 同时设置四个属性

# CSS3 transform变换(静态的效果) #

1. translate(x,y) 设置盒子位移
2. scale(x,y) 设置盒子缩放
3. rotate(deg) 设置盒子旋转
4. skew(x-angle,y-angle) 设置盒子斜切

CSS3 animation动画

1、@keyframes 定义关键帧动画
2、animation-name 动画名称
3、animation-duration 动画时间
4、animation-timing-function 动画曲线

- linear 匀速
- ease 开始和结束慢速
- ease-in 开始是慢速
- ease-out 结束时慢速
- ease-in-out 开始和结束时慢速
- steps 动画步数
  5、animation-delay 动画延迟
  6、animation-iteration-count 动画播放次数 n|infinite
  7、animation-direction

normal 默认动画结束不返回
Alternate 动画结束后返回
8、animation-play-state 动画状态

paused 停止
running 运动
9、animation-fill-mode 动画前后的状态

none 不改变默认行为
forwards 当动画完成后，保持最后一个属性值（在最后一个关键帧中定义）
backwards 在 animation-delay 所指定的一段时间内，在动画显示之前，应用开始属性值（在第一个关键帧中定义）
both 向前和向后填充模式都被应用
10、animation:name duration timing-function delay iteration-count direction;同时设置多个属性

# CSS浏览器前缀 #

## 浏览器样式前缀 ##

- 为了让CSS3样式兼容，需要将某些样式加上浏览器前缀：
```html
-ms- 兼容IE浏览器
-moz- 兼容firefox
-o- 兼容opera
-webkit- 兼容chrome 和 safari
```
## 自动添加浏览器前缀 ##

- 目前的状况是，有些CSS3属性需要加前缀，有些不需要加，有些只需要加一部分，这些加前缀的工作可以交给插件来完成，比如安装： autoprefixer

- Sublime text 中安装 autoprefixer 执行 preferences/key Bindings-Users 设置快捷键 { "keys": ["ctrl+alt+x"], "command": "autoprefixer" } 通过此工具可以按照最新的前缀使用情况给样式自动加前缀。

# HTML5新结构标签（在PC端不适用，不建议使用） #

- h5新增的主要语义化标签如下：

1. header 页面头部、页眉
2. nav 页面导航
3. article 一篇文章
4. section 文章中的章节
5. aside 侧边栏
6. footer 页面底部、页脚

# HTML5 新增表单控件（不建议使用，兼容性不好，不同的浏览器看到的结果不一样，基本不用） #

- 新增类型：网址 邮箱 日期 时间 星期 数量 范围 电话 颜色 搜索
```html
<label>网址:</label><input type="url" name="" required><br><br> 
<label>邮箱:</label><input type="email" name="" required><br><br> 
<label>日期:</label><input type="date" name=""><br><br> 
<label>时间:</label><input type="time" name=""><br><br> 
<label>星期:</label><input type="week" name=""><br><br> 
<label>数量:</label><input type="number" name=""> <br><br>
<label>范围:</label><input type="range" name=""><br><br> 
<label>电话:</label><input type="tel" name=""><br><br> 
<label>颜色:</label><input type="color" name=""><br><br> 
<label>搜索:</label><input type="search" name=""><br><br>
```
- 新增常用表单控件属性
1. placeholder 设置文本框默认提示文字
2. autofocus 自动获得焦点
3. autocomplete 联想关键词

# HTML5 音频和视频（不太重要） #

- html5增加了audio和video标签，提供了在页面上插入音频和视频的标准方法。

- audio标签 
支持格式：ogg、wav、mp3

- 对应属性：
1. autoplay 自动播放
2. controls 显示播放器
3. loop 循环播放
4. preload 预加载
5. muted 静音

举例：
```html
<audio src="source/audio.mp3" autoplay controls loop preload></audio>

<!-- 或者用如下方式：  -->

<audio  autoplay controls loop preload>
    <source src="source/audio.mp3" type="">
    <source src="source/audio02.wav" type="">
</audio>
source标签的作用是提供多个媒体文件地址，如果一个地址的文件不兼容，就使用下一个地址。
```
- video标签 
- 支持格式：ogg、mp4、webM

- 属性：
1. width
2. height
3. Poster

- 可选第三方播放器：(实际开发中使用该方法)
1. cyberplayer
2. tencentPlayer
3. youkuplayer