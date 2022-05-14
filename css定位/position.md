* position  
    1. static默认值，呆在文档流里
    2. relative相对定位，升起来，但不脱离文档流
    3. absolute绝对定位，定位基准是祖先里的非static
    4. fixed固定定位，定位基准时viewport（有诈）
    5. sticky粘滞定位，不好描述或者直接举例

* 经验
    1. 如果你写了absolute，一般补一个relative
    2. 如果你写了absolute或fixed，一定要补top和left
    3. sticky兼容性很差，主要用于面试装逼

* position：relative
    * 使用场景：
        1. 用于做位移（少）
        2. 用于给absolute元素做爸爸
    * 配合z-index：
        1. z-index：auto 默认值，不创建新层叠上下文
        2. z-index: -1 / 0 / 1
    * 经验：写z-index：9999的都是菜逼；学会管理z-index

* position：absolute
    * 使用场景：
        1. 脱离原来的位置，另起一层，比如对话框的关闭按钮
        2. 鼠标提示
    * 配合z-index
    * 经验：
        1. 很多菜逼都以为absolute是相对于relative定位的
        2. absolute相对于祖先元素中最近的一个定位元素（position不是static）定位
        3. 某些浏览器上如果不写top/left会位置错乱
        4. 善用left：100%
        5. 善用left：50% ,加负margin

* position：fixed（相对于视口定位）
    * 使用场景：
        1. 烦人的广告
        2. 回到顶部按钮
    * 配合z-index：
    * 经验：手机端尽量不要用这个属性，坑很多，搜一下【移动端fixed】
```
/*当父级元素加特殊属性会导致视口变成container*/
/*html*/
<div class="container">
<div class="fixed">*回顶部</div>
</div>
```
```
/*css*/
.container{/*正常属性*/}
.fixed{}
.container{transform: scale(0.9)};
```

* white-space：nowrap 文字内容不准换行
* 检查显示hover：Style点击hover，选中hover
* auto不等于0

