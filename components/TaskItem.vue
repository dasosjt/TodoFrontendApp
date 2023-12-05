<template>
	<li class="list-item" :class="{ done: status }">
        <span>
          <b-card>
              <b-card-header>
                {{id}} - {{title}}
              </b-card-header>
              <b-card-body class="text-right">
                 <b-card-text>
                  {{ content }}
                 </b-card-text>
              </b-card-body>
            <b-card-footer>
              <input
                type="checkbox"
                class="checkbox"
                :id="idComputed"
                @change="onTaskStatusChange"
                :checked="status">
              <b-btn variant="danger" @click="onTaskDelete">
                Delete
              </b-btn>
            </b-card-footer>
          </b-card>
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
