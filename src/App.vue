<script>
export default {
  name: 'App',
  data() {
    return {
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
      ]
    }
  }
}
</script>

<template>
  <h1>Todo List</h1>
  <ul>
    <li v-for="task in task">
      <span :style="{ textDecoration: task.done ? 'line-through' : '' }">{{ task.text }}</span>

    </li>
  </ul>
</template>

<style></style>
