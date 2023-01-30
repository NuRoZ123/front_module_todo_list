<template>
  <TaskComponent v-for="(_,index) of todos" :todo="todos[index]" v-bind:key="todos[index].title"/>
  <CreateTaskComponent @createTask="createTask"/>
</template>

<script>
import TaskComponent from './components/TaskComponent.vue';
import CreateTaskComponent from "@/components/CreateTaskComponent";

export default {

  name: 'App',
  components: {
    CreateTaskComponent,
    TaskComponent
  },

  data: () => ({
    todos: [
      {title: "la une", checked: false},
      {title: "la deux", checked: true},
      {title: "le trois", checked: true}
    ]
  }),

  methods: {
    createTask(title) {
      this.todos.push({title: title, checked: false})
    }
  }
}
</script>
