<template>
  <div class="inputListItem">
    <ul>
      <li v-for="i in list" :key="i">
        <span>{{i}}</span>
        <edit-to-do :i="i"></edit-to-do>
    </li>
  </ul>
  </div>
</template>

<script>
import EditToDo from './EditToDo.vue'

export default {
  props: ["list"],
  components:{
    EditToDo,
  },
  setup(){
 
    const showIcon = false
    let showIconFunc = function(){
      showIcon = !showIcon
  }
return{
  showIconFunc
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
