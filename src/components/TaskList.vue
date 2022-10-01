<template>
  <PureTaskList :tasks="tasks" @archive-task="archiveTask" @pin-task="pinTask" />
</template>

<script>
import PureTaskList from "./PureTaskList.vue";
import {useStore} from "vuex";
import {computed} from "vue";

export default {
  name: "TaskList",
  components: { PureTaskList },
  setup(){
    const store = useStore()

    const tasks = computed(() => store.state.tasks)

    const archiveTask = task => store.dispatch('archiveTask', task)
    const pinTask = task => store.dispatch('pinTask', task)

    return {
      tasks,
      archiveTask,
      pinTask,
    }
  }
}
</script>

<style scoped>

</style>
