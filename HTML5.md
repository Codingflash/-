# HTML5

## HTML5 概念

* 狭义：HTML发展到今天的第五代版本
* 广义：包括HTML、CSS、js以及浏览器机制等一系列新技术集合的描述

## HTML5特性

* \<!DOCTYPE html>相对于之前的HTML版本，更简单的文档声明，因为HTML5不再基于SGML来进行定义

* 语义化的标签  类似于div这样布局标签，从使用上来说和div没有任何区别，但是可以让代码的可读性更强，有利于开发人员的阅读和搜索引擎的读取（有利于SEO）

  > SEO  搜索引擎优化，网络运营人员

  * hearder  头部
  * nav  导航
  * hgroup  标题容器
  * article  文章
  * section  分节
  * figure  插入的内容
  * figcaption  插入内容的标题
  * aside  次要内容
  * main  主体
  * footer  底部
  * address  地址
  * time   时间
  * progress  进度

* 功能标签

  * audio  播放音频
  * video  播放视频
  * canvas  画布

* 新增的全局属性

  * hidden  隐藏某个元素
  * draggable  设置当前元素是否能被拖拽
  * contenteditable   设置当前元素是否能编辑内容
  * data-*  自定义属性，供css和js使用

* 表单类型

  * email   电子邮件
  * url   网址
  * date  日期
  * time   时间
  * week  周
  * month  月份
  * datetime-local   日期时间
  * search  搜索栏
  * color   颜色
  * number  数字
  * range  滑块

* 表单属性

  * form 
    * novalidate  提交表单时忽略表单验证
  * 表单控件
    * form  指定当前控件所在的表单
    * placeholder  设置表单控件的提示文字
    * autofocus  自动获得焦点
    * required  表示当前表单控件是必填项
    * pattern   用正则的方式进行验证
    * autocomplete  设置当前表单控件是否可以自动完成
    * number和range
      * min  最小值
      * max  最大值
      * step  步进值
    * submit 提交按钮，重写form属性
      * formaction   重写提交地址
      * formmethod   重写提交方式
      * formenctype  重写表单内容编码
      * formnovalidate  重写是否开启表单验证
      * formtarget  重写打开新页面的方式