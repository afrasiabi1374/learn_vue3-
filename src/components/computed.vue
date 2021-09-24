<template>
    <div>
        <input type="text" placeholder="first name" v-model="fName">
        <input type="text" placeholder="last name" v-model="lName">
        <h2>
            you full name is : {{fullName}}
        </h2>
    </div>
</template>

<script>
import {reactive,toRefs,computed} from 'vue'
export default {
 setup () {

     const state = reactive({
         fName :'',
         lName :''
     })
    const fullName = computed(()=>{
        return state.fName + state.lName
    })
    return {
        ...toRefs(state),
        fullName
     }
 }
}
</script>

<style>

</style>