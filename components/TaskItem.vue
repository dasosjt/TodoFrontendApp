<template>
	<li class="list-item" :class="{ done: status }">
        <input
          type="checkbox"
          class="checkbox"
          :id="idComputed"
          @change="onTaskStatusChange"
          :checked="status">
        <label class="mr-3" :for="idComputed"></label>
        <span>
          {{id}}
          <b-card-header>
            {{title}}
          </b-card-header>
          <b-card-body>
            {{ content }}
          </b-card-body>
          <b-btn-close class="icon-delete" @click="onTaskDelete">
            Delete
          </b-btn-close>
        </span>
    </li>
</template>

<script>
	export default {
        name: "TaskItem",
        props: {
            id: {
                type: Number,
                default: 0
            },
            title: {
                type: String,
                default: ""
            },
            content: {
              type: String,
              default: ""
            },
            status: {
                type: Boolean,
                default: false
            }
        },
        computed: {
            idComputed() {
                return `item-${this.id}`
            }
        },
        methods: {
            onTaskStatusChange(e) {
                const checked = e.target.checked
                this.$emit("eventTaskStatusChange", this.id, checked)
            },

            onTaskDelete(e) {
                console.log("onTaskDelete");
                this.$emit("eventTaskDelete", this.id)
            }
        }
    }
</script>
