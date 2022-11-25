<template>
  <div class="inputListItem">
    <ul>
      <li style="list-style:none" v-for="i in list" :key="i" >
        <span v-show="showIcon">{{i}}</span>
        <edit-to-do :i="i" @updateList="showIconFunc"></edit-to-do>
      </li>
  </ul>
  </div>
</template>

<script>
import EditToDo from './EditToDo.vue'
import { ref } from 'vue'

export default {
  emits:['hideList'],
  props: ["list"],
  components:{
    EditToDo,
  },
  setup(){
 
    let showIcon = ref(true)
    let showIconFunc = function(){
      showIcon.value = !showIcon.value
      }
return{
  showIconFunc,
  showIcon
}
  }

};
</script>

<style scoped>
.inputListItem {
  background-color: aquamarine;
  width: 400px;
  height: auto;
  margin: auto;
  display: flex;
  margin-top: 50px;
  flex-direction: row;
  overflow: hidden;
  border-radius: 15px;
  box-shadow: 5px 5px 20px 5px #888888;  
}

.editButton{
margin-left: 20px; 
}

</style>
