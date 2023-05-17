<!-- TOC -->autoauto- [css](#css)auto- [Array](#array)auto- [String](#string)auto- [JSON介绍](#json介绍)auto- [Window](#window)auto- [DOM](#dom)autoauto<!-- /TOC -->
## css
1. css选择器
   元素选择器：  h1{   }  
   id选择器：  #id属性值 {}
   类选择器：   .class属性值{  }    .cls {  }  ``` <h1  class='cls'>Css class selector </h>```
2. 视频10
   音视频标签： audio video  ；加入control标签
   换行： ```<br>```；空格：```&nbsp```;  ***<br> 标签表示换行（line break） "horizontal rule"（水平线）<hr>***
   文本加粗：```<strong><b>```
   css样式： text-height:   text-indent:(缩进)  text-align:（）水平对齐方式
3. 页面布局
   频繁使用div span两个没有语义的布局标签
   特点：  
   * div
      (1).  一行只显示一个，独占一行；
      (2).宽度为默认父元素的宽度，高度由内容撑开；
      (3).可以设置宽高（width,height）
   * span标签
     （1）.一行显示多个，
      （2）宽度和高度由默认内容撑开；
      （3）.不可以设置宽高； 
   CSS盒子模型 ：
   组成：content(内容)、padding（内边距）、border（边框）、外边距（maigin）；
   CSS属性：
   margin:上、右、下、左；
   盒子组成的属性；

   * 表格与表单标签：
     （1）.表格标签
     ```
          <table>;  定义表格整体，可以包含多个<tr>,  属性：border:边框宽度； width:表格宽度； cellspacing:单元之间的空间；
          <tr>:表格的行，可以包含多个<td>
          <td>:表格单元格，可以包含内容；     如果是表头单元格，可以使用<th>;  
      ```   
      (2). 表单标签
          场景：负责数据采集，如注册、登录等数据采集
          标签：```<form>```
          表单项：不同类型的input元素、下拉列表、文本域；
          ```  <input> ```定义表单项，通过type属性控制输入形式。               buttom,submit,hidden,number,time,file,data,
          ```  <select>```定义下拉列表；                                      下拉列表子选项通过option定义；
          ```  <textarea>```定义文本域；
         属性：action:规定当提交表单时向何处发送表单数据；url；
               method：规定用于发送表单数据的方式：get post;    get：在url后面拼接表单数据，比如：？username=Tom&age=12,url长度有限，默认值；  post：在消息体（请求体）中传递，参数大小无限制。
         type取值：
         text,  默认项，定义单行的输入字段；
         password, 定义密码字段；
         radio,  定义单选按钮
         checkbox,   定义复选框；
         file,     定义文件上传按钮；
         date/ time/datatime-local  定义日期/时间/日期时间
         number   定义数字输入框；
         email   定义邮件输入框
         hidden     定义隐藏域
         submit/reset/button    定义提交/重置/可点击按钮
               
## Array
   * 属性：length;
   * 方法：1. forEach()；遍历数组中每一个有值元素，并调用一次传入的函数；
           2.push();  将新元素添加到数组的末尾，并返回数组长度； 
           3.aplice();从数组中删除元素；
## String
* String字符串对象的创建方式有两种:
      1.var/let 变量名 = new String("-");
      2.var/let 变量名 = “-”；
* 属性
   length; 字符串的长度；
* 方法
   charAt();           返回指定位置的字符；
   indexof();           检索字符串
   trim();              去除字符串两边的空格；
   substring();          提取字符串两个指定的索引号之间的字符；
## JSON介绍
  javascript object notation;javascript对象标记法；
  JSON是通过javascript对象标记法书写的文本；
* 定义
  var/let 变量名 = '{"变量名1" = value1,"变量名2"= value2,}';
  value的数据类型为：数字（整数or浮点数），字符串（在双引号内），逻辑值（true 或false）,数组(在方括号中)，对象（在花括号）,null；
* JS对象与字符串的转换：
  1.JSON字符串转换为JS对象；
  ```
   var jsobject = JSON.parse(userstr);
   ```
  2.JS对象转换为字符串：
  ```
    var/let jsonStr = JSON.string(jsObject);  
  ```

## Window
介绍：浏览器窗口对象；
获取：直接使用window,其中window可以省略。window.alert("hello") ;  alert("hello");
属性：（1）history,对History对象只读引用；
      （2）location:对窗口或框架的Location对象。
      （3）navigator:对Navigator对象的只读引用；
方法：（1）alert:显示带有一段消息和一个确认按钮的警告框；
      （2）confirm:显示带有一段消息以及确认按钮和取消按钮的对话框；
      （3）sentInerval():按照指定的周期（以毫秒）来调用函数或表达式。
      （4）setTimeout():在指定的毫秒后调用函数或计算表达式。
   * location:   地址栏对象；
   获取：使用window.location获取；其中window.可以省略；
   属性：href:设置或返回完整的URL；    ``` wondow.loacation.href = "www....."  ```

## DOM
概念：Document Object Model,文档对象模型；
javascript通过DOM，就能够对HTML进行解析：
     * 改变HTML元素的内容；
     * 改变HTML元素的样式；（CSS）
     * 对HTML DOM事件做出反应；
     * 添加和删除HTML元素；
DOM是W3C的标准，定义了访问HTML和XML文档的标准，分为三个不同的部分：


## vue
1. vue快速入门
 * 新建html文件，引入vue.js文件
   ``` <script src = "js/vue.js></script>   //官方提供js文件
 * 在js代码区域，创建vue核心对象，定义数据类型
   ```
   <script>
   new Vue({
      el:"#app"   //el表示vue要控制的区域；   #为id选择器
      data:{
         message:"hello vue!"
      }
   })
 * 编写试图 
   ```
   <div id="app">
   <input type ="text" v-model="message">  //绑定
   {{message}}   //
   </div>
***插值表达式***
形式：{{}}
内容可以是：
   *变量
   *三元运算符
   *函数调用
   *算术运算
### 常用指令
* v-bind    为HTML标签绑定属性值，如设置href，css样式
* v-mdoel    在表单元素上创建双向数据绑定
* v-on       为HTML标签绑定事件
* v-if
* v-else-if       //条件性的渲染某元素，判定为true时渲染，否则不渲染
* v-else
* v-show      根据条件展示某元素，区别在于切换的是display属性的值
* v-for       列表渲染，遍历容器的元素或对象的属性

* v-bind    为HTML标签绑定属性值，如设置href，css样式
  ```
  <a v-bind:href="url">百度</a>
  <a :href="url">baidu</a>
  <script>{
   new Vue({
      el:"#app",   //接管区域
      data:{
         url:"www.baidu.com"
      }
   })
  }
  </script>
  ```
* v-mdoel    在表单元素上创建双向数据绑定
  ```
  <input type="test" v-model="url">
  ```
  ***通过v-bind或者v-model绑定的变量，必须在数据模型中声明；*** 
* v-on       为HTML标签绑定事件
  ```
  <input type="button" value="按钮" v-on:click="handle()">
  <input type="button" value="按钮" @click="handle()">
  <script>
    new Vue({
      el:"#app",
      data:{
         ...
      }
      methods:{
         handle:function(){
            alert("被点击了")；
         }
      }
    })
    ```
* v-if
  ```
  {{age}}  //定义数据模型
  <span v-if="age <=25">年轻人</span>
   <span v-else-if="age">35 && age <60">中年人</span>
  <span v-else>老年人</span>
  ```
* v-show      根据条件展示某元素，区别在于切换的是display属性的值
  ```
  <span v-show = "age <=35">年轻人</span>
  ```
* v-for       列表渲染，遍历容器的元素或对象的属性
  ```
  <div v-for="addr in addrs">{{addr}}</div>   //通过插值表达式将遍历出的元素在视图中展现出来;插值表达式可以使用算术运算的。
  <divv-for="(addr,index) in addrs">{{index}}</div>   //需要拿到索引，则使用这种方式
  data:{
   ...
   addrs:['北京','上海','深圳']
  }，
  ```
## Ajax
(Asynchronous JavaScript and Xml,异步的javaScrtipt 和XML)
1. 作用：
  * 数据交换：通过Ajax可以给服务器发送请求，并相应服务器的数据；
  * 异步交互：可以在不重新加载整个页面的情况瞎，与服务器交换数据并更新部分网页的技术，如：搜索联想、用户名是否可用的校验。
2. ***异步与同步***
 同步：客户端发送请求后等待服务器的相应；
 异步：客户端发送请求后，可以执行其他操作；不需要等待服务器相应；
3.  **原生Ajax**
   * 数据地址：http://yapi.smart-xwork.cn/mock/169327/emp/list
   * 创建XMLHttpRequest对象：用于和服务器交换数据
   * 想服务器发送请求
   * 获取服务器相应数据
  
### Axios
1. 入门
 * 引入Axios的js文件
    ```
    <script scr="./axios.min.js">
    ```
 * 使用Axios发送请求，并获取相应结果
```
 axios({
   method:"get",
   url:"http://yapi.smart-xwork.cn/mock/169327/emp/list"
 }).then((result)=>{                      //成功回调函数
   console.log(result.data) 
 });         
axios({
   method:"post",
   url:"http://yapi.smart-xwork.cn/mock/169327/emp/list",
   data="id=1"
}).then((result)=>{
   console.log(result.data);
})
```
## 前后端分离开发
* 前后端混合开发
  1.沟通成本高
  2.分工不明确
  3.不便管理与维护 扩展
接口文档：
  前后端
  来源：需求+原型
### YAPI:api管理平台
* api接口管理
* MOck服务
### 前端开发工程化
* 模块化
* 组件化
* 规范化
* 自动化
#### 环境准备
1. vue-cli
   介绍：vue官方提供的脚手架，用于快速生成一个Vue的项目模板
   功能：
      **统一的目录结构**
      **本地调试**
      **热部署** //代码变动不需要再次运行就可以加载最新的程序
      **单元测试**
      **集成打包上线**
   依赖环境：NodeJS     //工程化工具
2. Vue项目-创建
   方法1：命令行：vue create vue-project01
   方法2：通过图形化界面：vue ui  //注意，要用管理员身份运行cmd

3. 运行：
    npm run server //需要到项目文件内部
    在vs中通过npm启动
   停止：
    ctrl + c
### element组件库
1. 安装
    npm install element-ui@2.15.3
2. 引入ElementUI组件库
   import ElementUI from 'element-ui';
   import 'element-ui/lib/theme-chalk/index.css';
   Vue.use(ElementUI);                                 //在main.js中
   
3. 使用 
    去官网查找想要使用的组件，使用提供的代码；
    * 在app.vue中引入使用的vue文件；  ```<ElementView></ElementView>```
    * 常见组件：table表格、button按钮、pagination分页、Dialog对话框、form表单；
  
  * 代码用法：
    在 Vue 中，export default {} 是一个用于导出组件选项对象的语法。它是用来定义 Vue 组件的配置信息和功能的地方。通过这种方式，可以将组件的选项对象导出供其他文件或组件使用。
    在 Vue 组件中，export default {} 的作用如下：
    1）、定义组件选项：export default {} 中的大括号内部是一个对象，用于定义组件的各种选项，如数据、方法、生命周期钩子、计算属性、样式等。你可以在这个对象中配置组件的行为和特性。
    2）模块化导出：通过使用 export default，可以将组件作为一个独立的模块导出，使其可以在其他地方导入和使用。这样做可以帮助组织代码结构，并允许你在其他组件中引用该组件。

### 案例
 