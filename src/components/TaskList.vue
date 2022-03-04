<template>
  <div v-show="taskList.length > 0">
    <div class="tasklist">
      <task-item
        v-for="task in taskList"
        :key="task.id"
        :task="task"
        @removeTask="$emit('removeTask', task)"
      />
    </div>
  </div>
  <h2 v-show="taskList.length == 0" class="tasklist_title">Задач нет</h2>
</template>

<script>
import TaskItem from "@/components/TaskItem";

export default {
  components: {
    TaskItem,
  },

  props: {
    taskList: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.tasklist_title {
  margin-bottom: 10px;
}
</style>