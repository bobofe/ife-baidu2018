## 给菜单添加样式
###遇到的问题
1、层叠样式，样式失效问题

2、使用border-bottom颜色消失，但是长度不变，说明使用border-bottom不合适

3、点击之后，样式不消失

4、使用动画库



### 解决方法

1、给事件方法触发所加的class名前加之前的class

```css
.menu{
    margin-bottom: 10px;
    border-bottom: 10px solid transparent;
    transition: border-bottom-color 2s ease-in,color 2s ease-in;
}
.menu.active{
    border-bottom-color:black;
    color: red;
}
```

2、在menu下面增加一个元素，设置width，通过width设置样式

问题：设置transition的时候，长度是从一边增大的，不是从中间增大

解决：给设置width的元素加一个margin: 0 auto;这样样式就从中间开始增大

3.点击切换添加和移除样式

`element.classList`

+ **add**( String [, String] )：添加指定的类值。如果这些类已经存在于元素的属性中，那么它们将被忽略。

+ **remove**( String [,String] )：删除指定的类值。

+ **item**( Number )：按集合中的索引返回类值。

+ **toggle** ( String [, force] )：当只有一个参数时切换 class value; 即如果类存在，则删除它并返回`false`，如果不存在，则添加它并返回`true`。当存在第二个参数时：如果第二个参数的计算结果为true，则添加指定的类值，如果计算结果为false，则删除它

+ **contains**( String )

检查元素的类属性中是否存在指定的类值。

+ replace( oldClass, newClass )：用一个新类替换已有类。

