<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style>
.btn {
  padding: 10px;
  font-size: 20px;
  background: none;
  border: 4px solid lightseagreen;
  border-radius: 10px;
}
</style>