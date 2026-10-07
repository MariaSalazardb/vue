<script>
export default {
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increment() {
      this.counter++;
    },
  },
};
</script>

<template>
  <h2>App</h2>
  <button @click="increment">{{ counter }}</button>
</template>
