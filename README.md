2015.10.21 杭州银货通面试 目前看来未通过
1.link和import的区别，当时没答出来， 因为自己的确不知道是什么区别，哎，css写的还是比较少啊。现在看一下，区别如下：
首先，他两的作用相同，唯一的区别是服务对象不同，@import是为css服务，link是为当前的页服务。本质上，这两种都是为了加载css，但还是存
在一些细微的差别：
 (1) 老祖宗的差别。link属于XHTML标签，而@import完全是CSS提供的一种方式。link标签除了可以加载CSS外，还可以做很多其它的事情，比如定
 义RSS，定义rel连接属性等，@import就只能加载CSS了。
 (2) 差别2：加载顺序的差别。当一个页面被加载的时候（就是被浏览者浏览的时候），link引用的CSS会同时被加载，而@import引用的CSS会等到
 页面全部被下载完再被加载。所以有时候浏览@import加载CSS的页面时开始会没有样式（就是闪烁），网速慢的时候还挺明显（梦之都加载CSS的
 方式就是使用@import，我一边下载一边浏览梦之都网页时，就会出现上述问题）。
 (3) 差别3：兼容性的差别。由于@import是CSS2.1提出的所以老的浏览器不支持，@import只有在IE5以上的才能识别，而link标签无此问题。现在已
 经放弃ie5,6,7了，所以兼容性方面没什么区别。
 (4) 差别4：使用dom控制样式时的差别。当使用javascript控制dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的。
 
 谷歌使用的是在页面写，因为对于速度的要求比较高。
