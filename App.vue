<template>
  <div id="app">
    <h1>Parent Component</h1>

    <input v-model="parentPlaceholder" placeholder="" />

    <h3>Shared Data: {{ sharedData }}</h3>

    <ChildOne :message="sharedData" @update-message="updateSharedData" />
    <ChildTwo :message="sharedData" @update-message="updateSharedData" />

    <ChildThree :placeholder-text="parentPlaceholder" @update-placeholder="updatePlaceholder" />
  </div>
</template>

<script>
import ChildOne from './components/ChildOne.vue';
import ChildTwo from './components/ChildTwo.vue';
import ChildThree from './components/ChildThree.vue';

export default {
  name: 'App',
  components: {
    ChildOne,
    ChildTwo,
    ChildThree,
  },
  data() {
    return {
      sharedData: "", 
      parentPlaceholder: "", 
    };
  },
  methods: {
    updateSharedData(newData) {
      this.sharedData = newData;
    },
    updatePlaceholder(newPlaceholder) {
      this.parentPlaceholder = newPlaceholder;
    },
  },
};
</script>

