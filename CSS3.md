# CSS3

## css3新增选择器

* 标签选择器，类名选择器，id选择器，群组选择器，交叉选择器，后代选择器
* 通用选择器 *  所有元素
* 属性选择器
  * [属性名]  拥有当前属性的所有元素
  * [属性名=属性值]  拥有当前属性并且值为特定值的所有元素
  * [属性名*=属性值]  拥有当前属性并且值中包含特定值的所有元素
  * [属性名^=属性值]  拥有当前属性并且值以特定值开始的所有元素
  * [属性名$=属性值]  拥有当前属性并且值以特定值结束的所有元素
* 子选择器    选择器1>选择器2     选择器1选中的所有元素的字元素中能够被选择器2选择的元素  
* 相邻选择器

  * 选择器1+选择器2  紧邻在选择器1能够选中的元素后面被选择器2选中的元素
  * 选择器1~选择器2   在选择器1能够选中的元素后面被选择器2选中的元素
* 根据相对位置选择器
  * 所有元素的相对位置
    * :first-child   当前所有兄弟元素中的第一个
    * :last-child   当前所有兄弟元素中的最后一个
    * :nth-child(2/2n/2n-1/3n/5n)当前所有兄弟元素指定的位置
    * :nth-last-child(2/2n/2n-1/3n/5n)当前所有兄弟元素指定的位置，倒数
    * :only-child没有任何兄弟元素
  * 所有相同兄弟元素的相对位置
    * :first-of-child   当前所有同类兄弟元素中的第一个
    * :last-of-child   当前所有同类兄弟元素中的最后一个
    * :nth-of-child(2/2n/2n-1/3n/5n)当前所有同类兄弟元素指定的位置
    * :nth-last-of-child(2/2n/2n-1/3n/5n)当前所有同类兄弟元素指定的位置，倒数
    * :only-of-child没有任何同类兄弟元素
* 根据元素的内容进行选择
  * :empty    选择没有任何子元素或任何文本内容的元素
* 伪类选择器
  * :link  未被访问过的链接
  * :hover  鼠标经过时的效果
  * :active  鼠标按下链接时的效果
  * :visited  访问过的链接
* 根据表单特性的选择
  * :focus  选择获得焦点呢的表单控件
  * :enabled  选择所有未被禁用的表单控件
  * :disabled   选择禁用的表单控件
* :not{选择器)  选择除了被当前选择器选中的元素
* ::selection   内容当中被选择区域的样式
* 伪元素选择器
  * ::before  在当前元素内容之前插入另一段内容
  * ::after   在当前元素内容之后插入另一段内容
  * content属性  必须设置，表示当前伪元素的内容
  * :first-line  选择第一行文本内容
  * :first-letter  选择第一个字母/文字



## CSS选择器优先级的计算规则

* 选择器优先级是靠A、B、C、D四个值进行计算的，比较优先级的时候依次比较ABCD四个值的大小
  * A  如果有内联样式，则A的值为1，否则为0，也就是1，0，0，0
  * B  根据当前id选择器出现的次数，出现几次，B就为几，0，1，0，0
  * C  根据当前的类选择器、伪类选择器、属性选择器出现的次数来计算0，0，1，0
  * D 根据标签选择器和伪元素选择器出现的次数来计算  0，0，0，1
* *通用选择器是没有优先级权重的
* 在某个样式后面设置!important，那么当前样式就具备最高的优先级，比行内样式还要高
  *  如果有选择器优先级更高的选择器内给样式同样设置!important会比优先级更低的选择器内的!important，或者直接在当前样式后覆盖

## css3新增属性

* 容器修饰
  * border-radius圆角
    * 1个值  四个圆角相同的半径
    * 2个值   左上右下，右上左下
    * 3个值   左上，右上左下，右下
    * 4个值  左上、右上、右下、左下
    * 对于每个角落，我们都可以设置1个半径，也可以设置2个半径
    * 可以用百分比来表示，宽度的百分比会作为横向的半径，高度的百分比会作为纵向的半径
    * 圆角会影响元素的边框显示，但不会影响布局
  * box-shadow/text-shadow
    * 值的含义   横向偏移  纵向偏移   模糊程度   阴影大小  阴影颜色   内阴影/内发光
    * text-shadow  用法类似，但是不能设置内阴影
    * 可以同时设置多组值 -- 实现多重边框
    * 不会对于布局产生任何影响
  * outline  、outline-offset  轮廓线
    * outline和border 类似 ，outline-style、outline-width、outline-color
    * outline-offset  轮廓线向外偏移的值
    * 不会对布局产生任何影响
    * 轮廓线不会随着元素圆角的变化而变化
  * 背景属性的补充
    * background-clip  用来调整背景图片的显示区域
      * border-box 默认值
      * padding-box
      * context-box
    * background-origin  用来调整背景图片的定位原点
      * border-box 
      * padding-box  默认值
      * context-box
    * background-size     调整背景图片的大小
      * 数值
      * 百分比
      * cover  等比例缩放图片，直到能够把元素内部覆盖满
      * contain  等比例的缩放图片直到能够把图片显示为止
    * 背景属性也可以设置多组值
  * 图片边框
    * border-image-source  图片的地址
    * border-image-width  边框图片的宽度
    * border-image-slice  对图片截取的方式
    * border-image-outset  图片边框向外的偏移值
    * border-image-repeat   边框部分的图片的重复方式
  * 渐变图案
    * 在所有能够使用图片的地方都可以用渐变图案表示
    *  linear-gradient()   线性渐变
    * repeating-linear-gradient()    重复线性渐变
    * radial-gradient  径向渐变
    * repeating-radial-gradient重复的径向渐变
  * 过渡动画
    * transition-property 表示前有哪些欸属性需要过渡效果
      * all 全部属性都应用过渡效果
    * transition-duration表示当前过渡动画的持续时间
    * transition-timing-function速率函数
      * linear 匀速
      * ease-in 加速
      * ease-out减速
      * seae-in-out县加速后减速
      * cubic-bezier()通过贝塞尔曲线设置速度变化
    * transition-delay延迟时间
    * translate对以上属性进行集合
  * transform 转换\变形
    * 2D转换
      * 位移
        * translateX()
        * translateY()
        * translate()
      * 旋转
        * rotate
          * 角度 deg
          * 弧度  1rad
      * 缩放
        * scaleX()
        * scaleY()
        * scale()
      * 斜切
        * skewX()
        * skewY()
        * skew()
      * 同时设置多个转换效果，用逗号隔开给个转换函数即可
      * transform-origin  设置位移基准点，可以设置到图形的外部
    * 3D转换
      * 位移
        * tanslateZ()
        * translate3d()
      * 旋转
        * rotateX()
        * rotateY()
        * rotateZ()
        * rotate3d()
      * 缩放
        * scaleZ()
        * scale3d()
      * 单独设置景深
        * perspective()
      * 设置场景的景深 perspective
      * 设置容器和子元素之间的呈现方式
        * transform-style :  preserve-3d
      * 设置观察者的位置
        * perspective-origin 
      * 设置元素背面是否可见
        * backface-visibility:hidden;
  * 帧动画
    * 定义动画
      * @keyframes 动画名称{from{} to{}}
      * @keyframes 动画名称{05{} 2-%{}}
    * 调用动画
      * animation-name  动画名称
      * animation-duration  动画的持续时间
      * animation-timing-function   动画的速率变化趋势
      * animation-delay   首次动画的延迟
      * animation-iteration-count   动画运行的次数
        * infinite  无限次
      * animation-fill-mode  动画完成时的状态
      * animation-direction 动画的播放方式
      * animation-play-state 动画的播放状态
      * animation: name duration timing-function delay iteration-count direction fill-mode;
* 弹性布局
  * 容器
    * display：flex对于当前容器应用弹性布局
    * justify-content  调整项目在主轴方向上的分布方式
      * flex-start  对齐到主轴的起点
      * flex-end  对齐到主轴的终点
      * center  居中主轴的中心
      * space-around  均匀分布主轴上的项目，项目和项目之间的间距是项目和容器之间间距的2倍
      * space-between  均匀的分布主轴上的项目，项目和容器之间没有边距，项目和项目之间的间距完全相等
    * align-items  调整一行内容在交叉轴方向上的对齐方式
      * flex-start  对齐到交叉轴的起点
      * flex-end  对齐到交叉轴的终点
      * center  居中交叉轴轴的中心
      * stretch  如果项目没有设置高度，则在交叉轴方向上拉伸直到占满交叉轴为止
      * baseline  项目当中的文字和容器中的文字基线对齐
    * flex-warp  调整项目的换行方式
      * no-wrap 不换行
      * wrap  普通换行
      * wrap-reverse   换行  第一行在最后
    * flex-direction  调整主轴的方向
      * row  水平  从左到右
      * row-reverse  水平从右到左
      * column 垂直，从上到下
      * column-revsrse  垂直，从下到上
    * align-content  调整多行项目在交叉轴方向上的分布方式
      - flex-start  对齐到交叉轴的起点
      - flex-end  对齐到交叉轴的终点
      - center  居中交叉轴的中心
      - space-around  均匀分布交叉轴上的项目，项目和项目之间的间距是项目和容器之间间距的2倍
      - space-between  均匀的分布交叉
      - 轴上的项目，项目和容器之间没有边距，项目和项目之间的间距完全相等
      - stretch  如果项目没有设置高度，则在交叉轴方向上拉伸直到占满交叉轴为止
    * flex-low对于flew-warp和flex-direction的简写
  * 项目
    * order  指定当前项目在所有项目中的排序，默认为0，排序方式  从大到小，相同大小原始顺序
    * flex-grow   当前项目在主轴方向上的剩余控件分配中要占据几份，分配的空间会被当前项目占据
    * flex-shrink   当前项目在主轴方向上，空间不足时缩小的比例，默认1，每个项目默认都会缩小
    * flex-basis   在当前项目未设置宽高的情况下，在主轴方向上占据的大小
    * flex是对flex-grow、flex-shrink、flex-basis 的简写
    * align-self  单独设置当前项目在交叉轴方向的对齐方式

* 多栏/多列布局  控制文字显示效果的
  * column-width  指定当前每一栏的宽度
  * column-count   指定当前要划分成几栏
  * column-gap   指定两栏之间的间距
  * column-rule  指定两栏之间的分割线样式
  * column-fill   指定内容的对齐方式，默认均匀分布
    * auto  自动将每一列的高度占满才换到下一列
    * balance  每一列的高度都是一致的
  * column-span  设置某个元素的内容可以跨越多列

* box-sizing:border-box;让当前width和height变为整个容器的宽高（内容、内边距、边框）

* 字体引入和字体图标

  * 在css3当中允许直接引入一个指定的字体文件

    ```css
    @font-face {
            font-family: "name";
            src: url(font.ttf);
        }
    ```

  * 利用次特性，我们可以将项目需要的图标封装到字体文件中使用

    * 借助于AI软件  导出字体文件
    * 借助在线平台    生成自定义字体图标库  阿里巴巴  iconfont

* 图片精灵

  * 把我们要在浏览器展示的多个小图标、小土拍你放置到一张大的图片当中。目的是为了提高网页加载速度
  * background-position

* 响应式布局

  * 书写一套代码，让页面可以在不同的终端设备有不同的显示效果，能够最合理方式去适应当前的分辨率

  * 实现响应式布局的原理
    * 百分比实现流式布局
    * 媒体查询   media query  让部分css代码在特定的设备和分辨率范围下起作用
      > @media  设备名  条件(查询范围){css代码}

        * 设备名字
          * screen 屏幕设备
          * print  打印设备
          * all  全部
      * 条件
        * and  包括
        * or   或者
        * not   排除
      * 查询范围
        * min-width  最小宽度   也就是分辨率大于当前值的时候
        * max-width  最大宽度   也就是分辨率小于当前值的时候

  * 12栅格化

    * 在页面响应式变化的过程，对于一行浮动元素要进行方便的控制