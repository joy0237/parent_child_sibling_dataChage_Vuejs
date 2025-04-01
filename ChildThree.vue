<template>
    <div>
      <h2>Child Three (Placeholder Sync with Parent)</h2>
      <input v-model="inputValue" :placeholder="placeholderText" @input="sendPlaceholder" />
      <p>Current Placeholder: {{ placeholderText }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ["placeholderText"],
    data() {
      return {
        inputValue: "",
      };
    },
    watch: {
      placeholderText(newValue) {
        this.inputValue = newValue;
      },
    },
    methods: {
      sendPlaceholder() {
        this.$emit("update-placeholder", this.inputValue);
      },
    },
  };
  </script>
    