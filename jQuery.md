# 初识 jQuery

#### jQuery 如何获取元素
```
$(document) //选择整个文档对象

$('#myId') //选择ID为myId的网页元素

$('div.myClass') // 选择class为myClass的div元素

$('input[name=first]') // 选择name属性等于first的input元素
```
#### jQuery 的链式操作是怎样的
对它进行一系列操作，并且所有操作可以连接在一起，以链条的形式写出来
```
$('div').find('h3').eq(2).html('Hello')
```
#### jQuery 如何创建元素
```
$('<p>Hello</p>');

$('<li class="new">new list item</li>');

$('ul').append('<li>list item</li>');
```
#### jQuery 如何移动元素
```
//移动到p元素前面
$('div').insertAfter($('p'));
//移动到p元素后面
$('p').after($('div')
```
#### jQuery 如何修改元素的属性
```
$('p').addClass()
为p的元素添加指定的样式类名
$('p').removeClass()
移除p中每个匹配元素上一个，多个或全部样式。
$('p').height()
设置p元素的高度值。
```
