<template>
  <li>
    <span v-bind:class="{ done: item.completed }">
      <input type="checkbox" v-on:change="item.completed = !item.completed" />
      <strong>{{ index + 1 }}</strong>
      {{ item.title }}
    </span>
    <button class="del" v-on:click="$emit('remove-item', item.id)">
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
    index: Number,
  },
};
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}

.del {
  background: red;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}

.done {
  text-decoration: line-through;
}

input {
  margin-right: 1rem;
}
</style>