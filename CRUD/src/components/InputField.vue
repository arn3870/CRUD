<template>
    <div class="inputContainer">
      <p style="" class="ToDo">What needs to be done?</p>
      <input
        type="text"
        class="inputField"
        v-model="inputField"
        @keydown.enter="inputFunc"
      />
      <button class="submitButton" @click="inputFunc">Submit</button>
    </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup(props, context) {
    let inputField = ref("");
   let inputFunc = function () {
      context.emit('updated', inputField.value)
      // console.log("============input", inputField.value
      // )
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
input{
  background-color: #edf5e1;
}
.inputContainer {
  margin-top: 100px !important;
  width: 300px;
  height: 200px;
  border-radius: 15px;
  box-shadow: 5px 5px 20px 5px #379683;  
  margin: auto;
  padding: 30px;
  display: flex;
  flex-direction: column;
  background-color: #05386B;
}
.submitButton {
  display: flex;
  margin: auto;
  background-color: #379683;
  border: none;
  border-radius: 10px;
  font-weight: bolder;
  color: #edf5e1;
}
.inputListClass {
  margin-top: 200px;
  width: auto;
  height: 200px;
  margin: 200px;
  background-color: aqua;
}
.ToDo{
  margin:auto;
  color: #edf5e1;;
  font-family: monospace;
  font-weight: bold;
  font-size: 15px;
}
</style>
