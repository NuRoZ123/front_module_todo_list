<template>
  <input v-model="title">
  <button v-on:click="sendToMainNewTask">Confirmer</button>
</template>

<script>
export default {
  name: "CreateTaskComponent",
  data: () => ({
    title: "",
  }),

  methods: {
    sendToMainNewTask() {
      this.$emit("createTask", this.title);
      this.title = "";
    }
  }
}
</script>

<style scoped>

</style>