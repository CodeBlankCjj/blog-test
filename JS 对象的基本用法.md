# JS 对象的基本用法

### 想用对象，那么必须先拥有对象，怎么创建对象
```
let obj = new Object({
  '属性名1': '属性值1',
  '属性名2': '属性值2'
})
```
- 规范写法  let obj = new Object({ 'name': '苍井空', 'age': '18' })
- 简写写法  let obj2 = { 'name': '泷泽萝拉', 'age': '21' }

```
注：属性名遵守标识符的规则（不遵守则报错）,可不加引号，其他情况自动转换为字符串
let obj = {
  1: 'a',           //   1: "a"
  3.2: 'b',         //   3.2: "b"
  1e2: true,        //   100: true
  1e-2: true,       //   0.01: true
  .234: true,       //   0.234: true
  0xFF: true        //   255: true
}
```
![image](https://user-images.githubusercontent.com/81228918/118636674-845e8180-b807-11eb-90f1-c0e2347e7849.png)<br/>
变量可以当成属性名但需要特殊方式<br/>
![image](https://user-images.githubusercontent.com/81228918/118637005-ea4b0900-b807-11eb-83d1-a4a99bbf5e00.png)<br/>
### 怎么增加对象的属性
```
obj.gender = '女';
```
![image](https://user-images.githubusercontent.com/81228918/118638735-ba046a00-b809-11eb-90ee-638726714d5f.png)
### 怎么删除对象的属性
```
delete obj.name || delete obj['name']
```
![image](https://user-images.githubusercontent.com/81228918/118638827-d0aac100-b809-11eb-8033-886b7d492839.png)
### 怎么修改对象的属性
```
obj.name = "xiao";
obj.age = "20";
```
![image](https://user-images.githubusercontent.com/81228918/118639246-444cce00-b80a-11eb-9f3b-144ee75de1a6.png)

### 怎么查看对象的属性
```
//查看自身属性
Object.keys(obj);
```
![image](https://user-images.githubusercontent.com/81228918/118639414-76f6c680-b80a-11eb-88dd-4f75a3e470d6.png)
### 'name' in obj和obj.hasOwnProperty('name') 的区别
- in 是查看自己和原型上是否含有这个属性
- hasOwnProperty是查看自己身上是否含有这个属性
