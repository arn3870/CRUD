<template>
  <div class="inputListItem">
    <ul>
      <li class="listLine" v-for="(i, index) in list" :key="i">
        <span v-show="HideListItem"> {{ index }}. {{ i }}</span>
        <!-- <button @click="onC($event, i)"></button> -->
        <edit-to-do
          :i="i"
          :listIndex="index"
          @deleteListItem="changeData(listIndex)"
          @switchEdit="showIconFunc"
          @newUpdatedListValue="updatedValue"
        ></edit-to-do>
      </li>
    </ul>
  </div>
</template>

<script>
import EditToDo from "./EditToDo.vue";
import { ref } from "vue";

export default {
  emits: ["hideList"],
  props: ["list"],
  components: {
    EditToDo,
  },
  setup(props, context) {
    let HideListItem = ref(true);
    let actualInputData = ref("");
    let mutateList = ref(props.list)

    let changeData = (listIndex) => {
      mutateList.value.splice(listIndex, 1);
    };

    let showIconFunc = () => {
      HideListItem.value = !HideListItem.value;
    };
    let updatedValue = (obj) => {
      mutateList.value[obj.editIndex] = obj.finalData
      console.log(">>>>>>>>>>>>>>>", obj);

    }
    return {
      showIconFunc,
      HideListItem,
      actualInputData,
      changeData,
      updatedValue
    };
  },
};
</script>

<style scoped>
.inputListItem {
  background-color: #05386B;
  color: #edf5e1;
  font-family: monospace;
  font-size: large;
  width: 400px;
  height: auto;
  margin: auto;
  display: flex;
  margin-top: 50px;
  flex-direction: row;
  overflow: hidden;
  border-radius: 15px;
  box-shadow: 5px 5px 20px 5px #379683;
}
.listLine{
  list-style: none;
  display: flex;
}
</style>
