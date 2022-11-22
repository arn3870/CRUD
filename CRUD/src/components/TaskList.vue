<template>
  <div class="inputListItem">
    <h1></h1>
    <ul>
      <li v-for=" inpt in inputArray" :key="inpt"> {{ inpt }}</li>
    </ul>
  </div>
</template>

<script>
export default{
  props:{
    inputArray : Object
  },
  setup(props) {
    return{
    }
  },
  mounted(){
    console.log(">>>>>>>>>>>>>>>>>>>>>" + this.inputArray)
  }
}
</script>

<style scoped>
.inputListItem{
background-color: aquamarine;
width: 300px;
height: 300px;
margin: auto;
display: flex;
margin-top: 50px
}
</style>
