<template>
  <form @submit.prevent="onSubmit" class="Application">
    <input type="text" v-model="name" placeholder="First name" />
    <div v-if="nameError" class="text">Please enter your first name</div>
    <br />
    <br />
    <input type="text" v-model="surname" placeholder="Last name" />
    <div v-if="surnameError" class="text">Please enter your last name</div>
    <br />
    <button @click="identification">Sign in</button>
    <br />
    <div v-if="successMessage" class="title">Good Job!</div>
  </form>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      nameError: false,
      surname: "",
      surnameError: false,
      successMessage: false,
    };
  },
  methods: {
    identification() {
      if (!this.name) {
        this.nameError = true;
        this.surnameError = false;
      } else if (!this.surname) {
        this.nameError = false;
        this.surnameError = true;
      } else {
        this.nameError = false;
        this.surnameError = false;
        this.successMessage = true;
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
.Application {
  font-family: sans-serif;
}
.Application input {
  width: 250px;
  height: 44px;
  border: 1px solid lightgray;
  border-radius: 5px;
  outline: none;
  padding-left: 10px;
  transition: all 0.2s ease;
}
.Application input:focus {
  border: 1px solid #070720;
}
.Application button {
  margin-top: 10px;
  width: 250px;
  height: 44px;
  border: 1px solid lightgray;
  background-color: transparent;
  border-radius: 5px;
  transition: all 0.2s ease;
  cursor: pointer;
}
.Application button:hover {
  border: 1px solid gray;
}
.Application .text {
  margin-top: 20px;
}
.Application .title {
  margin-top: 10px;
}
</style>
