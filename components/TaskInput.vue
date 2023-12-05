<template>
  <b-card>
    <b-card-body>
      <form @submit="onAddNewTask">
        <input type="text" placeholder="Title" v-model="title" required>
        <input type="text" placeholder="What needs to be done?" v-model="content" required>
        <b-button type="submit">Add Task</b-button>
      </form>
    </b-card-body>
  </b-card>
</template>

<script>
export default {
  name: "TaskInput",
  data() {
    return {
      title: "",
      content: ""
    }
  },
  methods: {

    onAddNewTask(e) {
      e.preventDefault()
      const taskTitle = this.title
      const taskContent = this.content
      this.$emit("eventAddNewTask", taskTitle, taskContent)
      this.title = ""
      this.content = ""
    }

  }
}
</script>
