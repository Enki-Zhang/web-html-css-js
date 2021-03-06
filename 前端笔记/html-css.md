## 关于clearfix

**目的**：如何将多个块级元素在一行内显示。就需要引出 ***浮动定位***。
文档流：显示的内容都是占位，块元素上下显示 独占一行，内联元素：水平显示，左右显示。
而浮动可以让改变块元素的排列方式，让内容从上下排显示变为水平显示。
特点：

* 浮动元素会被排除在文档流之外，如同漂浮在文档的上方（不占据页面的空间）其余元素要上前部补位。不占位 盒子重叠，内容不重叠；
* 浮动元素会停靠在父元素的左边或右边，或停靠在其他已浮动元素的边缘上(元素只能在当前所在行浮动)，需要内容都水平排列，需要将所有的盒子都设置浮动。
* 浮动元素依然位于父元素之内,如果浮动的元素大于父元素的宽，显示不下就会另起一行，第二行显示.
* 浮动元素处理的问题-解决多个块级元素在一行内显示的问题。
* 浮动不占位的副作用只会同级之间产生，浮动的副作用都是往下影响，不会影响上边的盒子。
* 元素一旦浮动起来之后，元素的宽度将变成自适应(内容决定宽度)，前提：不指定元素宽度的情况下
* 元素一旦浮动起来之后，都将变成块级元素，尤其对行内元素影响较大
                块级元素：允许修改尺寸
                行内元素：不允许修改尺寸
* 文本，行内元素，行内块元素时采用环绕的方式来排列的，是不会被浮动元素压在底下的。

**浮动带来的影响**
由于浮动元素会脱离文档流，所以导致不占据页面空间，所以会对父元素高度带来一定影响。如果一个元素中包含的元素全部是浮动元素，那么该元素高度将变成0（高度塌陷）。
**高度塌陷**
如果父元素不设置高，或者设置最小高，父元素的高度由子元素撑开，一旦浮动后不占位,父元素高度会显示成0的状态。
方法：
~~~
.cf:before,.cf:after {
   content:"";
   display:table;
}
.cf:after { clear:both; }
~~~
