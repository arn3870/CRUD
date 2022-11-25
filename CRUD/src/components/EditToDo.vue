<template>
        <div>
        <input v-if="editInput" @keydown.enter="showIconsnButton" :value="i" type="text"/>
        <q-icon v-if="checkCrossIcon" @click="deleteListData" style="margin: 5px" name="fa-solid fa-check" />
        <q-icon v-if="checkCrossIcon" style="margin: 5px" name="fa-solid fa-xmark" />
        <button v-if="editButton" @click="showIconsnButton" >Edit</button>
        </div>
</template>
<script>
import { reactive, ref } from 'vue'
export default {
        props:['i'],
        setup(props, context) {
                let editInput = ref(false)
                let checkCrossIcon = ref(false)
                let editButton = ref(true)
                let deleteListData = function(){
                        props.i

                }
                let showIconsnButton = function(){
                        // checkIcon.value = !checkIcon.value
                        editInput.value = !editInput.value
                        checkCrossIcon.value = !checkCrossIcon.value
                        editButton.value = !editButton.value
                        context.emit('updateList')
                        console.log("<<<<<<<<<<<<<<<<<<<");
                }
                // context.emit('hideList')

                return{
                   editInput,
                   checkCrossIcon,
                   editButton,
                   showIconsnButton,
                   deleteListData
                }
        },
}
</script>