<template>
  <div class="tasks-wrapper">
    <div :key="task.id" v-for="task in tasks">
      <Task
        @delete-task="$emit('delete-task', task.id)"
        @toggle-reminder="$emit('toggle-reminder', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: {
      type: Array,
      default: [],
    },
  },
};
</script>

<style scoped>
.tasks-wrapper {
    max-height: 50vh;
    overflow: auto;
}
</style>
