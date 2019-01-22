<template>
  <div class="item">
    <li>{{ title }}</li>
    <button v-on:click="$emit('remove')">Remove</button>
  </div>
</template>

<script>
export default {
  name: "todoItem",
  props: {
    title: String
  }
};
</script>
<style scoped>
.item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
</style>

