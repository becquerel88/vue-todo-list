<template>
  <div class="app">
    <header class="herader">
      <h2 class="header_title">Список задач</h2>
      <my-button @click="showDialog">Создать</my-button>
    </header>

    <my-dialog v-model:show="dialogVsible">
      <task-form @createTask="createTask" />
    </my-dialog>

    <task-list v-bind:taskList="taskList" @removeTask="removeTask" />
  </div>
</template>

<script>
import TaskList from "@/components/TaskList";
import TaskForm from "@/components/TaskForm";

export default {
  components: {
    TaskList,
    TaskForm,
  },
  data() {
    return {
      taskList: [
        { id: 1, taskName: "Задача 1", taskDescription: "Описание 1" },
        { id: 2, taskName: "Задача 2", taskDescription: "Описание 2" },
        { id: 3, taskName: "Задача 3", taskDescription: "Описание 3" },
      ],
      dialogVsible: false,
    };
  },
  methods: {
    createTask(task) {
      this.taskList.push(task);
      this.dialogVsible = false;
    },
    showDialog() {
      this.dialogVsible = true;
    },
    removeTask(task) {
      this.taskList =  this.taskList.filter(t => t.id !== task.id);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Fira Code;
  background: black;
  color: white;
}

.app {
  padding: 30px;
}

.herader {
  margin-bottom: 30px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
</style>