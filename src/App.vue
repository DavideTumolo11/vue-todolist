<script>
export default {
  name: 'App',
  data() {
    return {
      newTask: '',
      task: [
        {
          text: 'learn HTML',
          done: true
        },
        {
          text: 'learn CSS',
          done: true
        },
        {
          text: 'learn Vue',
          done: false
        }
      ],

    }
  },
  methods: {

    addTask() {
      console.log('new task');
      this.task.push({ text: this.newTask, done: false });
    },

    removetask(index) {
      console.log('rimosso', index);
      this.task.splice(index, 1)
    },
  }
}
</script>

<template>
  <div class="container my-4">
    <div class="card p-3">
      <div class="card-body">
        <h1>Todo List</h1>
        <ul class="list-group" v-if="task.length > 0">
          <li class="list-group-item" v-for="(task, index) in task">
            <span :style="{ textDecoration: task.done ? 'line-through' : '' }">{{ task.text }}</span>

            <span v-on:click="removetask(index)">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-x-circle"
                viewBox="0 0 16 16">
                <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14m0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16" />
                <path
                  d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708" />
              </svg>
            </span>
          </li>
        </ul>
        <p v-else> non hai todo</p>

      </div>

      <div class="input-group mb-3">
        <input type="text" v-model="newTask">
        <button class="btn btn-dark" @click="addTask">Aggiungi</button>
      </div>

    </div>
  </div>
</template>

<style></style>
