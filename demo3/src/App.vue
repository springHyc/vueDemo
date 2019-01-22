<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div id="app-2">
      <span v-bind:title="message">鼠标悬停几秒钟查看此处动态绑定的提示信息！</span>
    </div>

    <ul id="example-1">
      <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    </ul>
    <TodoList msg="test"/>
    <div>
      <button v-on:click="counter += 1">Add 1</button>
      <p>The button above has been clicked {{ counter }} times.</p>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    TodoList
  },
  data: function() {
    return {
      ok: Math.random(10) % 2 == 1 ? true : false,
      loginType: "username",
      message: "页面加载于 " + new Date().toLocaleString(),
      items: [{ id: 1, name: "张三" }, { id: 2, name: "李四" }],
      counter: 0
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
