## 任务一：给菜单添加样式
### 思路一：transition + 添加/移除class

问题：点击一下，下面的线不会自己消失，需要通过toggle来控制线的消失和重现

见task1-增加额外元素+transtion.html

### 思路二：transition + animation +  添加/移除class

点击一下，可以实现线的自动消失和重现

### 遇到的问题

1、层叠样式，样式失效问题？

2、使用border-bottom颜色消失，但是长度不变，说明使用border-bottom不合适？

3、如何操作class？

4、批量操作css？

5、线如果用伪类，无法居中变化

6、使用animation时，单次点击有效，双次点击无效（先添加后移除一个属性的操作）？

7、使用动画库

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

2、在menu下面增加一个元素或添加一个伪元素，设置width，通过width设置样式

问题：设置transition的时候，长度是从一边增大的，不是从中间增大

解决：给设置width的元素加一个margin: 0 auto;这样样式就从中间开始增大

3、点击切换添加和移除样式

`element.classList`

+ **add**( String [, String] )：添加指定的类值。如果这些类已经存在于元素的属性中，那么它们将被忽略。

+ **remove**( String [,String] )：删除指定的类值。

+ **item**( Number )：按集合中的索引返回类值。

+ **toggle** ( String [, force] )：当只有一个参数时切换 class value; 即如果类存在，则删除它并返回`false`，如果不存在，则添加它并返回`true`。当存在第二个参数时：如果第二个参数的计算结果为true，则添加指定的类值，如果计算结果为false，则删除它

+ **contains**( String )：检查元素的类属性中是否存在指定的类值。

+ replace( oldClass, newClass )：用一个新类替换已有类。

4、通过**element.style.cssText**批量操作css

5、暂时无解

6、先添加后，设置定时器移除

7、css动画库

Animate.css：

+ <https://daneden.github.io/animate.css/>

+ 简单动画库，操作一个元素进/出的动画

Animejs：

+ [https://animejs.com](https://animejs.com/)、<https://github.com/juliangarnier/anime/>

+ Anime.js（/æn.ə.meɪ/）是一个轻量级JavaScript动画库，具有简单但功能强大的API。它适用于CSS属性，SVG，DOM属性和JavaScript对象。

Hover.css：

- CSS hover 悬停效果，可以应用于链接、按钮、图片等等。
- [github.com/IanLunn/Hov…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2FIanLunn%2FHover)

wow.js:

- 滚动展示动画
- WOW.js 依赖 animate.css，所以它支持 animate.css 多达 60 多种的动画效果。
- [github.com/matthieua/W…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2Fmatthieua%2FWOW)

scrollReveal.js：

- 类似 wow.js
- [github.com/jlmakes/scr…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2Fjlmakes%2Fscrollreveal)

Magic.css：

- css3 animation动画库
- [github.com/miniMAC/mag…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2FminiMAC%2Fmagic)

Waves：

- 点击波纹效果
- [github.com/fians/Waves](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2Ffians%2FWaves)

move.js：

- 一个小型的JavaScript库，通过JS来控制一系列的CSS动画顺序执行，使CSS3动画变得非常简单和优雅。
- [github.com/visionmedia…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2Fvisionmedia%2Fmove.js)

Velocity.js：

- 一个功能齐全的 JavaScript 动画套件，包括诸如淡入淡出、滚动、滚动、停止、结束、翻转等动画效果。
- [github.com/julianshapi…](https://link.juejin.im?target=https%3A%2F%2Fgithub.com%2Fjulianshapiro%2Fvelocity)

## 




