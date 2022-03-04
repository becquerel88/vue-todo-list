<template>
  <form @submit.prevent class="form">
    <h2 class="form_title">Создание задачи</h2>
    <my-input
      v-model="task.taskName"
      type="text"
      placeholder="Задача" />
      
    <my-input
      v-model="task.taskDescription"
      type="text"
      placeholder="Описание задачи"
    />
    <my-button @click="createTask" class="form_btn">Добавить задачу</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      task: {
        taskName: "",
        taskDescription: "",
      },
    };
  },
  methods: {
    createTask() {
      this.task.id = Date.now();
      this.$emit("createTask", this.task);
      this.task = {
        taskName: "",
        taskDescription: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  margin-bottom: 30px;
}

.form_title {
  margin-bottom: 20px;
}

.form_btn {
  align-self: flex-end;
  margin-bottom: 10px;
}
</style>