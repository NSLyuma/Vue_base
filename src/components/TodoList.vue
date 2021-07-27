<template>
  <div>
    <ul>
      <TodoItem
        v-for="(item, i) in todos"
        v-bind:item="item"
        v-bind:index="i"
        :key="item.id"
        v-on:remove-item="removeItem"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue";
export default {
  name: "TodoList",
  components: {
    TodoItem,
  },
  props: ["todos"],
  methods: {
    removeItem(id) {
      this.$emit("remove-item", id);
    },
  },
};
</script>

<style scoped>
/* благодаря scoped стили будут видны только в этом компоненте */
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>