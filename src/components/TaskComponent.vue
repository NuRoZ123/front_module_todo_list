<template>
  <label :class="{ended: isChecked}">{{ todo.title }}
    <input type="checkbox" v-model="isChecked">
  </label>
</template>

<script>
export default {
  name: "TaskComponent",
  props: ["todo"],

  data: () => ({
    isChecked: false,
  }),

  mounted() {
    this.isChecked = this.todo.checked;
  },
}
</script>

<style scoped>
.ended {
  text-decoration: line-through;
}
</style>