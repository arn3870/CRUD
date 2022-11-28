<template>
  <div>
    <input
      v-if="editInput"
      @keydown.enter="updateListData"
      v-model="abc"
      type="text"
    />
    <q-icon
      v-if="checkCrossIcon"
      @click="updateListData"
      class="checkIcon"
      name="fa-solid fa-check"
    />
    <q-icon
      v-if="checkCrossIcon"
      @click="removeIcons"
      class="crossIcon"
      name="fa-solid fa-xmark"
    />
    <button v-if="editButton" @click="enableEditing">Edit</button>
  </div>
</template>
<script>
import { ref } from "vue";
export default {
  props: ["i", "listIndex"],
  setup(props, context) {
    let editInput = ref(false);
    let checkCrossIcon = ref(false);
    let editButton = ref(true);
    let updatedInputValue = ref("");
    let abc = ref(props.i);

    let removeIcons = () => {
      editInput.value = false;
      checkCrossIcon.value = false;
      context.emit("deleteListItem", props.listIndex);
    };

    let updateListData = () => {
      abc.value = abc.value;
      const obj = { finalData: abc.value, editIndex: props.listIndex };
      context.emit("newUpdatedListValue", obj);
    };

    let enableEditing = () => {
      // checkIcon.value = !checkIcon.value
      editInput.value = !editInput.value;
      checkCrossIcon.value = !checkCrossIcon.value;
      editButton.value = !editButton.value;
      context.emit("switchEdit", props.listIndex);
    };

    return {
      editInput,
      checkCrossIcon,
      editButton,
      enableEditing,
      removeIcons,
      updateListData,
      updatedInputValue,
      abc,
    };
  },
};
</script>

<style>
input{
  background-color: #edf5e1 ;
}
.crossIcon {
  font-size: large;
  color: red;
  margin: 5px;
}
.checkIcon {
  color: green;
  font-size: large;
  margin: 5px;
}
.crossIcon:hover {
  font-size: x-large;
}
.checkIcon:hover {
  font-size: x-large;
}
button{
  margin-left: 5px;
  background-color: #379683;
  border: none;
  border-radius: 10px;
  color: #edf5e1;
  font-family: monospace;
}
</style>
