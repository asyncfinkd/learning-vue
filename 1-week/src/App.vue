<template>
  <div class="body">
    <div>Counter: {{ counter }}</div>
    <div class="flex:buttons">
      <button @click="increment">Increment</button>
      <button @click="decrement">Decrement</button>
      <button @click="defaultCounter">Default</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increment() {
      this.counter++;
    },
    decrement() {
      this.counter--;
    },
    defaultCounter() {
      this.counter = 0;
    },
  },
};
</script>

<style scoped>
.body {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
  font-family: sans-serif;
  gap: 10px;
}
.flex\:buttons {
  display: flex;
  align-items: center;
  gap: 20px;
}
</style>