
<template>
  <div>
    <h1>{{msg}}/{{testTitle}}/{{testTitle2}}</h1>
    <form v-on:submit.prevent="addNewTodo">
      <label for="new-todo">Add a todo</label>
      <input v-model="newTodoText" id="new-todo" placeholder="E.g. Feed the cat">
      <button>Add</button>
    </form>
    <ul>
      <!-- <li
        is="todo-item"
        v-for="(todo, index) in todos"
        v-bind:key="todo.id"
        v-bind:title="todo.title"
        v-on:remove="todos.splice(index, 1)"
      ></li>-->
      <todoItem
        v-for="(item, index) in todos"
        v-bind:key="item.id"
        v-bind:title="item.title"
        v-on:remove="todos.splice(index, 1)"
      />
    </ul>
  </div>
</template>


<script>
import Vue from "vue";
import todoItem from "./todoItem.vue";

export default {
  name: "TodoList",
  props: {
    msg: String,
    testTitle: String,
    testTitle2: String
  },
  components: {
    todoItem
  },
  data: function() {
    return {
      newTodoText: "",
      todos: [
        {
          id: 1,
          title: "Do the dishes"
        },
        {
          id: 2,
          title: "Take out the trash"
        },
        {
          id: 3,
          title: "Mow the lawn"
        }
      ],
      nextTodoId: 4
    };
  },
  methods: {
    addNewTodo: function() {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText
      });
      this.newTodoText = "";
    }
  }
};
</script>

<style>
</style>
