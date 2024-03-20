<template>
  <div id="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <Header @add="handleAddTodo"></Header>
        <Body :list="todoList"></Body>
        <Footer></Footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Body from "./components/Body.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Body,
    Footer,
  },
  data() {
    return {
      todoList: [
        { name: "吃饭", id: 1, status: false },
        { name: "睡觉", id: 2, status: false },
        { name: "跑步", id: 3, status: false },
        { name: "游泳", id: 4, status: false },
        { name: "学习", id: 5, status: false },
      ],
    };
  },
  provide: () => {
    return {};
  },
  methods: {
    handleAddTodo(data) {
      this.todoList.push(data);
    },
  },
};
</script>

<style>
@import "./style/index.css";
</style>
