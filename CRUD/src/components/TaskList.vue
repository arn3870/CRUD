<template>
  <div class="inputListItem">
    <ul>
      <li v-for="i in list" :key="i">{{ i }}</li>
    </ul>
  </div>
</template>

<script>

export default {
  props: ["list"],

};
</script>

<style scoped>
.inputListItem {
  background-color: aquamarine;
  width: 300px;
  height: 300px;
  margin: auto;
  display: flex;
  margin-top: 50px;
  flex-direction: row;
}

</style>
