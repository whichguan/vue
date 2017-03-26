# vue练习
1. 安装cnpm ，代替npm。nodejs的包管理器

   ````javascript
   npm install -g cnpm --registry=https://registry.npm.taobao.org
   ````

2. 安装vue 

   ````javascript
   # 全局安装 vue-cli
   cnpm insatll -g vue-cli
   vue -V
   ````

   ​

3. 初始化

   ````javascript
   # 创建一个基于 webpack 模板的新项目
   vue init webpack my-project
   ````

   ​

4. 安装package.json里面的依赖

   ```javascript
   cnpm install
   ```

5. 跑起来

   ```java
   cnpm run dev
   ```



## Vue.js的一个组件（*.vue）

- html

  ```html
  <template></template>
  ```

- Javascript

  ```html
  <script></script>
  ```

- css

  ```html
  <style></style>
  ```

  ​

### 模板指令

1. 数据渲染 **v-text v-html  {{ }}**

   ```html
   {{ c }}
   <div v-text:='c'></div>
   <div v-html:='c'></div>
   ```


2. 逻辑判断 **v-if  v-show**

   ```html
   // 代码不输出
   <p v-if="isShow"></p>
   <p v-elae></p>
   // 代码css隐藏
   <p v-show="isShow"></p>
   // v-else
   <div v-if="Math.random() > 0.5">大于0.5</div>
   <div v-else>小于0.5</div>
   // v-else-if
   <div v-if="type==='a'">A</div>
   <div v-else-if="type==='b'">B</div>
   <div v-else-if="type==='c'">C</div>
   <div v-else>Not A B C</div>
   ```

3. 循环列表 **v-for**

   ```html
   <ul>
   	<li v-for='item in list'>
     		<p v-text='item.title'></p>
     	</li>
   </ul>
   ```

   ​

4. 绑定属性值 **v-bind**

   ```html
   # 标准写法
   <div v-bind:class="show?'red':'orange'"></div>
   	# 简写
   <div :class="show?'red':'orange'"></div>
   # 对象语法
   <div :class="{red:show}"></div>
   	# 多个class
   <div class='main' :class="{red:show,orange:show2}"></div>
   # 数组语法
   <div :class="[showClass,errorClass]"></div>
   # 其他属性
   <a :href="url">链接</a>
   ```

   ​


### Vue组件的重要选项

1. data/数据

```javascript
new Vue({
  data:{
    a:1,
    b:[]
  }
})
```

```html
<p>{{ a }}</p>
```

2. methods/方法

   ```javascript
   new Vue({
     data:{
       a:1,
       b:[]
     },
      methods:{
   	doSomething:function(){
         console.log(this.a)
   	}
      }
   })
   ```

   ```html
   <p v-on:="doSomething()">
     {{ a }}
   </p>
   <button @="doSomething()">按钮</button>
   ```

3. watch/监听

   ```javascript
   watch:{
     'a':function(val,oldVal){
       console.log("监听："+ val,oldVal)
     }
   }
   ```

   ​

