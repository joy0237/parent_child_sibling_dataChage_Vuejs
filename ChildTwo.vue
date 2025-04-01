<template>
    <div>
      <h2>Child Two</h2>
      <p>Data from Parent: {{ message }}</p>
      <input v-model="messageInput" @input="sendToParent" />
    </div>
  </template>
  
  <script>
  export default {
    props: ["message"],
    data() {
      return {
        messageInput: this.message,
      };
    },
    watch: {
      message(newValue) {
        this.messageInput = newValue;
      },
    },
    methods: {
      sendToParent() {
        this.$emit("update-message", this.messageInput);
      },
    },
  };
  </script>

  