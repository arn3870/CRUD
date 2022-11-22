<template>
  <div>
    <InputField @updated="handleInput"></InputField>
    <TaskList :list="mainList"></TaskList>
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
    const mainList = ref([])

    const handleInput = (val) => {
      mainList.value.push(val)
    }

    return{
      handleInput,
      mainList
    }

    }
  }
</script>
