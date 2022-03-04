<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog_content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "my-dialog",
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    hideDialog() {
      this.$emit("update:show", false);
    },
  },
};
</script>

<style scoped>
.dialog {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  position: fixed;
}

.dialog_content {
  margin: auto;
  padding: 30px;
  background: black;
  border-radius: 10px;
  min-width: 600px;
  min-height: 350px;
}
</style>