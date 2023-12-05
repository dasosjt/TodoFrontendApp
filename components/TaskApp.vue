<template>
  <div class="ani-slideInDown row justify-content-center">
    <div class="col-lg-6">
      <TaskInput @eventAddNewTask="onAddNewTask"/>
      <ul class="list mt-3">
        <TaskItem
          v-for="item in itemList"
          :id="item.id"
          :key="item.id"
          :title="item.title"
          :content="item.content"
          :status="item.status"
          @eventTaskStatusChange="onTaskStatusChange"
          @eventTaskDelete="onTaskDelete" />
      </ul>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TaskInput from "@/components/TaskInput.vue"
import TaskItem from "@/components/TaskItem.vue"
import {Task} from "~/models/Task";

export default {
  name: "home",
  components: {
    TaskInput,
    TaskItem
  },
  data() {
    return {
      itemList: []
    }
  },
  methods: {

    async onAddNewTask(taskTitle, taskContent) {
      let task = {
        id: null,
        title: taskTitle,
        content: taskContent,
        status: false
      }

      try {
        const response = await fetch(`http://localhost:8080/api/v1/task/`, { method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify(task)
        })

        const newTask = await response.json()
        this.itemList.push(newTask)

      } catch (error) {
        console.error(error)
      }
    },

    async onTaskStatusChange(id, checked) {
      console.log(id, checked)

      let item = this.itemList.find(i => i.id == id)
      if (item) {
        item.status = checked

        try {
          const response = await fetch(`http://localhost:8080/api/v1/task/${id}`, { method: 'PUT',
            headers: {
              'Content-Type': 'application/json',
            },
            body: JSON.stringify(item)
          })
        } catch (error) {
          console.error(error)
        }

      }

      console.log(this.itemList)
    },

    async onTaskDelete(id) {
      console.log(id)

      try {
        const response = await fetch(`http://localhost:8080/api/v1/task/${id}`, { method: 'DELETE' })
      } catch (error) {
        console.error(error)
      }

      let index = this.itemList.findIndex(i => i.id == id)
      if (index > -1) {
        this.itemList.splice(index, 1)
      }

      console.log(this.itemList)
    },

    async loadItemList() {
      try {
        const response = await fetch('http://localhost:8080/api/v1/task/all')
        this.itemList = await response.json()
      } catch (error) {
        console.error(error)
      }

      console.log("this.itemList =", this.itemList)
    },

    updateItemList() {
      //this.loadItemList();
      //localStorage.setItem("VuejsTodo", JSON.stringify(this.itemList))
    }
  },
  mounted() {
    // Load item list from local storage
    this.loadItemList()
  },
  watch: {
    itemList: {
      handler(value) {
        console.log("item changed")

        // save to localStorage
        this.updateItemList()
      },
      deep: true
    }
  }
}
</script>
