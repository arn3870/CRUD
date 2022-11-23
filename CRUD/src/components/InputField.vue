<template>
  <div>
    <div class="inputContainer">
      <input
        type="text"
        class="inputField"
        v-model="inputField"
        @keydown.enter="inputFunc"
      />
      <button class="submitButton" @click="inputFunc">Submit</button>
    </div>
  </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup(props, context) {
    let inputField = ref("");
    let inputFunc = function () {
      context.emit('updated', inputField.value)
      console.log("============input", inputField.value
      )
      inputField.value = "";
    };
    
    return {
      inputField,
      inputFunc,
    };
  },
};
</script>
<style scoped>
.inputContainer {
  width: 300px;
  height: 200px;
  border-radius: 15px;
  box-shadow: 5px 5px 20px 5px #888888;  
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
