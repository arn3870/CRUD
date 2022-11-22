<template>
  <div>
    <InputField></InputField>
    <TaskList></TaskList>
  </div>
</template>

<script>
import { ref } from 'vue'
import InputField from 'src/components/InputField.vue';
import TaskList from 'src/components/TaskList.vue';


export default{
  
  name: 'MainLayout',
  components: {
  InputField,
  TaskList
  },

  setup () {

    }
  }
</script>
