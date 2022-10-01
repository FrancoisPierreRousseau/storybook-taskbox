<template>
  <div>
    <div v-if="error" class="page lists-show">
      <div class="wrapper-message">
        <span class="icon-face-sad" />
        <p class="title-message">Oh no!</p>
        <p class="subtitle-message">Something went wrong</p>
      </div>
    </div>
    <div class="page lists-show">
      <nav>
        <h1 class="title-page">Taskbox</h1>
      </nav>
      <TaskList />
    </div>
  </div>
</template>

<script>
import TaskList from "./TaskList.vue";

export default {
  name: "PureInboxScreen.vue",
  components: { TaskList },
  props: {
    error: { type: Boolean, default: false }
  }
}
</script>

<style scoped>

</style>
