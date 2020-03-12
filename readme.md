# BFC定义
在解释BFC之前，先说一下文档流。我们常说的文档流其实分为定位流、浮动流和普通流三种。而普通流其实就是指BFC中的FC。FC是formatting context的首字母缩写，直译过来是格式化上下文，它是页面中的一块渲染区域，有一套渲染规则，决定了其子元素如何布局，以及和其他元素之间的关系和作用。常见的FC有BFC、IFC，还有GFC和FFC。BFC是block formatting context，也就是块级格式化上下文，是用于布局块级盒子的一块渲染区域。


## 个人理解是：BFC就是一个有特定规则的区域，这块区域内的元素只遵循特定规则，不受外部影响。

## BFC内部规则。
    内部的Box会在垂直方向，一个接一个地放置。PS:感觉不是废话么
    Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠。
    每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
    BFC的区域不会与float box重叠。
    BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
    计算BFC的高度时，浮动元素也参与计算。
    相信这5个东西都看得有点懵~~所以接下来浓缩介绍最常用的规则整理。

    规则一：BFC是一块独立规则的区域，不受外部影响，而内部元素也不会影响到外部。
    规则二：清楚浮动。触发BFC后能感知得到浮动元素的存在。
    规则三：BFC感知得到浮动元素的高度。

## 如何触发BFC
    根元素
    float属性不为none
    position为absolute或fixed
    display为inline-block, table-cell, table-caption, flex, inline-flex
    overflow不为visible（常用）