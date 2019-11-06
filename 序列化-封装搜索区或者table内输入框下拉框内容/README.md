## v1.1
## tableSerializeV1.1.js :
   1.简化js
   
   2.$("#listTable").serializeTable({bind:""});
   
     2.1 bind属性简化，如上 如值为空 返回的则是 数组 如不为空  则返回的是对象数组
      
      ## serializeTable方法 
     2.2 移除参数<span style="color: green"> filter</span>
     2.3 移除参数<span style="color: green"> able</span>
     
   3.$("#listTable").serializeSearch({'resultType':"object"});//
        
         3.1 resultType属性为空 默认对象 如{name:'lisi',age:26}  
              否则返回字符串例如 "name=lisi&age=26"  
         3.2 移除参数<span style="color: green"> filter</span>
         3.3 移除参数<span style="color: green"> able</span>

   4.需要过滤的input select 等 加上class为need_ingore即可。

## 原始版本
## tableSerialize.js :序列化-封装搜索区或者table内输入框下拉框内容的小插件 
```
  var tables = $("#listTable").serializeSearch({'bind': { able: false}});
  //封装格式化 多table部分  
```
| 参数       | 作用   |类型    |  默认值 |必填 |
| --------   | -----:  |-----:  | :----:  |--- |
|  el  | 绑定的id |String  |   '' (例如上面的‘#listTable’)   |是|
| bind     | 绑定封装后的对象属性 |Object  |  'bind': { able: true}  |是 |
| able    | bind下的属性 | Boolean  |  true   |否 |
| filter    | 过滤不要的封装字段 | Array  |  []   |否 |



```
 ##var mains = $("#mainContent").serializeSearch({'resultType':"object"});
 //封装格式化 多搜索区域 将其变成url后参数或者整个对象
```
| 参数       | 作用   |类型    |  默认值 |必填 |
| --------   | -----:  |-----:  | :----:  |--- |
|  el  | 绑定的id |String  |   '' (例如上面的‘#mainContent’)   |是|
| bind     | 绑定封装后的对象属性 |Object  |  'bind': { able: true}  |否|
| able    | bind下的属性 | Boolean  |  true   |否 |
| filter    | 过滤不要的封装字段 | Array  |  []   |否 |
| resultType    | 结果类型 | Oject/String(默认)  |  实例score=100&age=10 |否 |


<p style="height:200px"><image src="https://github.com/ten-ken/image/blob/master/relate_img/search-head.png?raw=true"/></p>

这个目的在于传递参数或对象时 不需要挨个$（"xx"）.val()的方式 同时也避免了form的序列化方法把一些隐藏域传入 造成不必要的麻烦。
