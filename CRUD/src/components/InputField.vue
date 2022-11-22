<template>
  <div class="inputContainer">
    <input
      type="text"
      class="inputField"
      v-model="inputField"
      @keydown.enter="inputFunc"
    />
    <button class="submitButton" @click="inputFunc">Submit</button>
  </div>
  <div class="inputListClass">
    <ul>
      <li v-for="inpt in inputArray" :key="inpt">{{ inpt }}</li>
    </ul>
  </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup() {
    let inputField = ref("");
    let inputArray = [];
    let inputFunc = function () {
      inputArray.push(inputField.value);
      inputField.value = "";
    };
    const outgoals = computed(() => {
      return inputField;
    });
    return {
      inputField,
      inputFunc,
      inputArray,
      outgoals,
    };
  },
  // computed: {
  //   outgoals() {
  //     return this.inputField;
  //   },
  // },
};
</script>
<style scoped>
.inputContainer {
  width: 250px;
  height: 200px;
  margin: auto;
  padding: 30px;
  display: flex;
  flex-direction: column;
  background-color: aqua;
}
.submitButton {
  display: flex;
  margin: auto;
}
.inputListClass {
  margin-top: 200px;
  width: auto;
  height: 200px;
  margin: 200px;
  background-color: aqua;
}
</style>
