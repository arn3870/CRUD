<template>
        <div>
        <input v-if="editInput" @keydown.enter="showIconsnButton" :value="i" type="text"/>
        <q-icon v-if="checkCrossIcon" style="margin: 5px" name="fa-solid fa-check" />
        <q-icon v-if="checkCrossIcon" style="margin: 5px" name="fa-solid fa-xmark" />
        <button v-if="editButton" @click="showIconsnButton" >Edit</button>
        </div>
</template>
<script>
import { reactive, ref } from 'vue'
export default {
        props:['i'],
        setup() {
                let editInput = ref(false)
                let checkCrossIcon = ref(false)
                let editButton = ref(true)

                let showIconsnButton = function(){
                        // checkIcon.value = !checkIcon.value
                        checkCrossIcon.value = !checkCrossIcon.value
                        editButton.value = !editButton.value
                        console.log("<<<<<<<<<<<<<<<<<<<");
                }

                return{
                   editInput,
                   checkCrossIcon,
                   editButton,
                   showIconsnButton,
                }
        },
}
</script>