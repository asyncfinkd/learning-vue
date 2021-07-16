<template>
  <div class="Application">
    <div
      v-for="item in UsersData"
      :key="item.user_id"
      class="Application__item"
      @click="addItemToList(item)"
    >
      {{ item.name }} {{ item.surname }}
    </div>
    <button class="Application__button" @click="showMeResult">
      Show Me Result
    </button>
    <div v-if="this.showResultPopup">
      <div class="Application__backgroundBlackBlur" @click="showMeResult"></div>
      <div class="Application__Header">
        <h1>Your Result:</h1>
        <div
          v-for="item in SavedData"
          :key="item.user_id"
          class="Application__item"
        >
          {{ item }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      showResultPopup: false,
      UsersData: [
        {
          user_id: 0,
          name: "Nika",
          surname: "Shamiladze",
        },
        {
          user_id: 1,
          name: "Mark",
          surname: "Zuckerberg",
        },
        {
          user_id: 2,
          name: "Bill",
          surname: "Gates",
        },
        {
          user_id: 3,
          name: "Elon",
          surname: "Musk",
        },
      ],
      SavedData: [],
    };
  },
  methods: {
    addItemToList(item) {
      let fullName = item.name + " " + item.surname;
      this.SavedData = [...this.SavedData, fullName];
      console.log([...new Set(this.SavedData)]);
    },
    showMeResult() {
      this.showResultPopup = !this.showResultPopup;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}
.Application {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
}
.Application__item {
  width: 250px;
  height: 44px;
  border: 1px solid lightgray;
  border-radius: 5px;
  display: flex;
  align-items: center;
  padding-left: 10px;
  margin-top: 10px;
  cursor: pointer;
  transition: all 0.2s ease;
}
.Application__item:hover {
  border: 1px solid gray;
}
.Application__button {
  width: 250px;
  height: 44px;
  margin-top: 20px;
  border: 1px solid lightgray;
  outline: none;
  border-radius: 5px;
  background-color: transparent;
}
.Application__backgroundBlackBlur {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
}
.Application__Header {
  width: 500px;
  height: 500px;
  background-color: #fff;
  z-index: 999;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.Application__Header h1 {
  font-size: 24px;
}
</style>
