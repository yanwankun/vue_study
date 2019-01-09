

### 安装cnpm
``````
npm install -g cnpm –registry=https://registry.npm.taobao.org
``````
### 安装 vue-cli
``````
cnpm install -g vue-cli
``````
### 新建项目
``````
vue init webpack my-first-project
``````
### 进入项目
``````
cd my-first-project
cnpm install
npm run dev
``````
### 新建vue对象
``````
data 
methods 
watch
``````
### 模版方法
``````
<p>{{ a}}</p>
<p v-text="a"> </p>
<p v-html="a"> </p>
<p v-if="isShow"></p>
<p v-show="isShow"></p>
<li v-for='item in items'>
    <p v-text='item.label'></p>
</li>

<button v-on:click="doThis"></button>
<button @click="dothis"></button>

<img v-bind:src="imggeSrc">
<div :source="{red: isRed }"></div>
<div :class="[classA, classB]"></div>
<div :class="[classA,{classB: isB, classC:isC}]"></div>
``````