<template>
  <input
    :value="modelValue"
    @input="updateInput"
    class="form_input"
    type="text"
  />
</template>

<script>
export default {
  name: "my-input",
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput() {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style scoped>
.form_input {
  margin-bottom: 10px;
  padding: 10px;
  border: lightseagreen 4px solid;
  border-radius: 10px;

  font-size: 20px;
}

.form_input:focus {
  outline: none;
  box-shadow:  0px 0px 5px lightseagreen;
}
</style>