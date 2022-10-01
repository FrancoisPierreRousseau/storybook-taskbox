<template>
  <PureInboxScreen :error="error" />
</template>

<script>
import PureInboxScreen from "./PureInboxScreen.vue";
import { useStore } from 'vuex';
import {computed} from "vue";

export default {
  name: "InboxScreen",
  components: { PureInboxScreen },
  setup(){
    const store = useStore()

    const error = computed(() => store.state.error)
    return {
      error,
    }
  }
}
</script>

<style scoped>

</style>
