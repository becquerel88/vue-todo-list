<template>
  <div class="task">
    <div class="task_container">
      <h3 class="task_title">{{ task.taskName }}</h3>
      <p class="task_description">{{ task.taskDescription }}</p>
    </div>
    <div class="task_buttons">
      <my-button @click="$emit('removeTask', task)">Удалить</my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.task {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;

  padding: 20px;
  border: lightseagreen 4px solid;
  border-radius: 10px;
}

.task:not(:last-child) {
  margin-bottom: 20px;
}

.task_title {
  font-size: 24px;
}

.task_description {
  font-size: 20px;
  margin-top: 5px;
}
</style>