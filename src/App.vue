<template>
  <div id="app">
    <h1>To do application</h1>
    <AddItem @add-item="addItem" />
    <hr />
    <TodoList v-bind:todos="todos" @remove-item="removeItem" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList.vue";
import AddItem from "@/components/AddItem.vue";

export default {
  name: "App",
  components: {
    TodoList,
    AddItem,
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Убраться", completed: false },
        { id: 2, title: "Сделать ДЗ", completed: false },
        { id: 3, title: "Порисовать", completed: false },
      ],
    };
  },
  methods: {
    removeItem(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addItem(item) {
      this.todos.push(item);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
