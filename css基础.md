# CSS

## CSS概念

层叠样式表(Cascading Style Sheets,缩写为CSS,是一种样式表语言，用来描述HTML文档的呈现。CSS描述了在屏幕、纸质、音频等其它媒体上的元素应该如何被渲染的问题。

## CSS创建

* 文本类型的文档后缀名设置.css就可以
* 通过文本编辑器直接创建

## CSS打开

* css的运行时基于HTML的，一般只需要在HTML文件中引入或者嵌入css的代码，在浏览器中打开HTML，浏览器就会自动解析识别css代码

## CSS编写

* css使用方式

  * 外部引入的方式  \<link rel="stylesheet" href="1.css">
  * 页面内嵌入  \<style>\</style>
  * 标签内部设置行内样式 /内联样式\<div style="color:red">\</div>
  * 在css代码中进行导入 @import url(base:css)

* css选择器

  > 选择当前规则要控制的标签

  * 选择器的格式  选择器{样式}

  * 选择器分类
    * 标签选择器 标签名{}

    * 类名选择器   .类名{}

      > 标签的类名可以有多个，多个类名之间用空格隔开，顺序的前后没有区别

    * id选择器  #id{}

    * 群组选择器   选择器1，选择器2，选择器3{}

    * 交叉选择器  标签名.类名{}  标签名#id{}    .类名1.类名2{}

    * 后代选择器   选择器1 选择器2{}

  * 层叠性

    * 多个选择器是可以同时对一个元素进行样式控制的

  * 优先级

    > 层叠性会产生一个问题  样式冲突后如何解决 

    * 标签名交叉id优先级>id选择器优先级>标签交叉类名优先级>类名选择器的优先级>标签名选择器优先级
    * 选择器选的越精确 优先级越高
    * 组合使用某个选择器一定比单独使用某个选择器高

* css样式

  * 格式  样式名：样式值；

  * 文字样式
    * color：文字颜色
    * font-family 字体  可以设置多个  优先使用第一个  如果当前系统没有这个字体  会一次尝试后续的字体
    * font-size  文字大小
    * font-style 文字倾斜
    * font-weight  文本加粗
    * text-decoration 文本修饰
    * text-align  水平对齐
    * line-height  行高  当行高和容器高度一致是就可以实现垂直居中的效果

  * 布局样式
    * width：宽度

      * 值、数值、百分比（相比于父元素的宽度占比）
      * auto  不设置  宽度会自适应父元素的宽度（当前元素宽度加上边框加内边距会自动等于容器的宽度）
    * height：高度

      * 值、数值、百分比（相比于父元素的宽度占比）
      * auto 不设置  高度会由子元素撑开
    * border: 边框（复合样式）

      * border-left(复合样式)
      * border-right(复合样式)
      * border-top(复合样式)
      * border-bottom(复合样式)

      * border-width （复合样式）
        * border-left-width
        * border-right-width
        * border-top-width
        * border-bottom-width
      * border-style（复合样式）
        * border-left-style
        * border-right-style
        * border-top-style
        * border-bottom-style
      * border-color（复合样式）
        * border-left-color
        * border-right-color
        * border-top-color
        * border-bottom-color
    * margin 外边距（复合样式）

      * margin-top上边距
      * margin-bottom下边距
      * margin-left左边距
      * margin-right右边距
      * margin
        * 1个值  上下左右
        * 2个值   上下   左右
        * 3个值   上  左右    下
        * 4个值   上  右  下   左
      * 容器自动居中   margin:0 auto;
      * 不仅可以用于元素和元素之间   也可以用于子元素和父元素之间
    * padding  内边距（复合样式）

      * padding-left左内边距
      * padding-right右内边距
      * padding-bottom下内边距
      * padding-top上内边距
      * 只是用于父元素和子元素/文字内容之间  只设置给父元素
    * float浮动属性

      * left设置了浮动的元素，依次从左向右进行排列
      * left设置了浮动的元素，依次从从右向左进行排列
      * 浮动是用来让多个元素在一行当中显示，需要在一行显示的块元素，都需要添加浮动属性
      * 浮动会**脱离文档流**（没有设置浮动属性的元素会对设置浮动属性的元素**视而不见**）
      * 设置了浮动的元素在之前元素不是浮动元素的情况下，只能在当前行显示
      * 浮动元素是受父元素限制的
      * 当前容器的宽度不足以放置全部的浮动预算，位置不够的元素就会换行显示
      * 行元素/行内块级元素   设置浮动之后会具备块元素的特性，可以设置宽高，不再识别标签键空格
      * **浮动元素不会把没有设置高度或者高度设置为auto的父元素自动撑开**
        * 给父元素设置高度
        * 在浮动元素的最后面添加一个空的div，在这个div中设置clean:both（清除浮动元素的影响）
        * 给父元素设置overflow：hidden也可以解决
        * 利用伪元素清除浮动的影响
      * 浮动元素可以和行元素在一行显示的
    * background  背景颜色
      * background-color设置容器的背景颜色
      * background-image 背景图片地址 url()
      * background-repeat  设置背景图片的重复方式
        * no-repeat  不重复
        * repeat-x  在x轴重复
        * repeat-y  在y轴重复
        * repeat  默认值  全部重复
      * background-position
        * left   right  top   bottom  center  两两组合可以确定九个位置，如果只设置一个，另外一个默认为center
        * x轴偏移数值，y轴偏移数值，可以为负值
        * x轴百分比，y轴百分比
      * background-arrachment 设置当前的背景图片是否要固定到窗口的某个位置（不随着页面的滚动而滚动）
      * 所有这些属性都可以整合到background属性中
     * border-radius  圆角的半径
     * opacity 当前元素的不透明度，0表示完全透明，1完全不透明。
       * 当前元素的内部元素和文字内容也会使用当前父元素的透明度设置
     * overflow属性 处理内容超出当前容器后的显示效果
       * visible 超出后依旧可见
       * hiddle 超出后隐藏
       * scrool 通过滚动条进行显示（在ie浏览器会始终像是滚动条栏）
       * auto 如果高度未超出容器，不显示，高度超出显示滚动条栏
    * overflow-x  单独控制横向超出的效果
    * overflow-y  单独控制纵向超出的效果
    * display 转换元素的特性
      * block 转换为块元素
      * inline-block  转换为行内块级元素
      * inline  转换为行元素
      * none  隐藏元素，直接消失
    * table相关
      * border-collapse设置表格的边框和单元格的边框的重合方式
      * table-layout  用于设置当前表格列的宽度模式
        * fixed   固定宽度，不会随着内容的改变而改变
    * position  定位属性  确定元素自身在浏览器中的位置   每个元素默认都有定位属性
      * relative  相对定位   对于自身的位置和其他兄弟元素都没有直接的影响，相对定位脱离文档流的，虽然脱离了文档流，但是元素在文档流的位置依然会保留
      * absolute  绝对定位  会影响自身（margin：0 auto不起作用）和其他兄弟元素（对它视而不见），绝对定位会脱离文档流，并且页不会保留原本在文档流中的位置。
      * fixed  固定定位   会影响自身（margin：0 auto不起作用）和其他兄弟元素（对它视而不见），固定定位会脱离文档流，并且页不会保留原本在文档流中的位置。
      * 除了默认的定位值（static）以外，元素设置了其他定值以后就可以使用left,right,top,bottom四个属性了。
        * 相对定位   位置是相对于元素本身的位置来确定的位移的
        * 绝对定位   位置是相对于有定位属性的父元素来计算距离的，如果父元素没有定位属性，则相对于当前的可视区域
        * 固定定位  位置是相对于浏览器的窗口来计算距离确定的
      * 使用定位场景有哪些？
        * 如果某个元素相对于窗口固定则使用固定定位
        * 某个元素当中有多个子元素要重叠像是，使用绝对定位结合相对定位
        * 本身布局并不适合使用文档流，元素比较零散，分布没有规律,使用绝对定位结合相对定位
      * z-index  只有设置了相对定位、绝对定位、固定定位的元素才能使用。设置z轴上的排序，值为数字。
    * min-width、max-width、min-height、max-height分贝设置元素宽高在自动适应的情况下变换的
    * visibility
      * hidden 隐藏某个元素，等价于opacity：0；
* cursor  设置鼠标的样式
    
* 所有的文字样式都具备继承性   继承样式的优先级没有默认样式的继承性高
  
  * 处理文字样式意外的其他样式，可以通过设置inherit实现继承效果
  
* 所有的CSS属性并不是在每种标签中都通用的
  
    * width  height  text-align 在行元素中是不起作用的
    * margin-top、margin-bottom在行元素中是不起作用的


* css注释/*       */
* margin-top  bug 某个元素如果没有上边框，然后也没有上内边距它的第一个子 元素如何在没有浮动属性的情况下设置margin-top这个margin-top就会作用到父元素的身上