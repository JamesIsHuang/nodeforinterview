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
 
2.get和post的区别：这个问题已经不是第一次被问了，然而自己还是几乎没说出来什么，这个就是比较坑自己了，想进步就得学会总结。
(1)get用来向服务器请求（获取）数据，post用于提交要修改的数据

(2)get一般放在URL以variable=value的形式传参，在地址栏可见，请求可被缓存，可以保存在浏览器历史记录中,所以有人说这是不安全的。post则是放在http的消息主体中发送。

(3)get据说是有长度限制，2kb,post没有(我当时胡乱说了20个字节，也真是醉了）。其实这是错误的。

3.问到ajax,这个自己是的确不太会，然而jQuery的ajax的complete回调方法记不住这个实在是有点丢人。现在首先来写写jQuery的ajaxjquery.ajax([setting]) async:true,异步请求；beforeSend(XHR),cache:Boolean,设置为false将不再缓存。complete：请求后完成回调函数
（成功或失败后都调用）参数：XMLHttpRequest对象和一个描述请求类型的字符串。contentType：类型：string。发送信息至服务器时的内容编码类型。context：类型：Object 这个对象用于设置 Ajax相关回调函数的上下文。也就是说，让回调函数内this指向这个对象（如果不设定这个参数，那么 this 就指向调用本次 AJAX 请求时传递的 options 参数）。比如指定一个 DOM 元素作为 context 参数，这样就设置了 success 回调函数的上下文为这个 DOM 元素。data:类型 string 发送到服务器的数据，将自转化为字符串格式GET 请求中将附加在 URL 后。查看 processData选项说明以禁止此自动转换。必须为Key/Value格式。如果为数组，jQuery将自动为不同值对应同一个名称。如 {foo:["bar1", "bar2"]} 转换为 '&foo=bar1&foo=bar2'。

beforeSend
在发送请求之前调用，并且传入一个 XMLHttpRequest 作为参数。
error
在请求出错时调用。传入 XMLHttpRequest 对象，描述错误类型的字符串以及一个异常对象（如果有的话）
dataFilter
在请求成功之后调用。传入返回的数据以及 "dataType" 参数的值。并且必须返回新的数据（可能是处理过的）传递给 success 回调函数。
success
当请求之后调用。传入返回后的数据，以及包含成功代码的字符串。
complete
当请求完成之后调用这个函数，无论成功或失败。传入 XMLHttpRequest 对象，以及一个包含成功或错误代码的字符串。
然后ajax自己还是要去看

4.有问到事件冒泡的机制（这个自己就会阻止事件冒泡，机制自己的确是不大了解），现在来写：

在一个对象上触发某类事件（比如单击onclick事件），如果此对象定义了此事件的处理程序，那么此事件就会调用这个处理程序，如果没有定义此事件处理程序或者事件返回true，那么这个事件会向这个对象的父级对象传播，从里到外，直至它被处理（父级对象所有同类事件都将被激活），或者它到达了对象层次的最顶层，即document对象（有些浏览器是window）。
如何处理：e.stopPropagation，阻止了事件冒泡，return false还阻止了事件本身。

5.js的基本数据类型（null，undefined，string，Boolean，Number），这个居然愣住了，没想起来Number。然后问到string的一些函数，愣住了，说了tostring,tolocalstring,当然还有replace，match，test，我都没说，然后他就问js操作数组，我真的完全愣住了，都没想起来push,pop,remove,shift,unshift,splice这样的方法.这样人如何要你，真是坑到家了。其实string对象的方法有search，contat，split,slice,substring,substr,CharAt,indexof,lastindexof等，Array则有concat,push,pop,split,join(返回字符串值),shift(移除第一个元素），unshift(在开始位置增加一个元素，并返回该数组，），reverse，sort，slice返回数组片段，splice移除一个或几个元素，或者也可以在被移除的位置增加元素。这个回答的不好，直接就是pass了，确实是最基础的。

6.问了熟悉Java，然后说jsp是脚本语言，我也是醉了，jsp算是什么脚本语言。

7.最后问了绝对路径和相对路径的区别，我不明白问这个意义何在，绝对路径就是从根目录一直写下来，相对路径就是相对于当前目录的路径。我说当前是/，他说./也行，然后我傻逼的说了那是在Linux下使用的，坑了。
至此，面试结束，也宣告我面试失败。
