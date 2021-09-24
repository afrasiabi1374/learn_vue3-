<template>
    firstName : <input type="text" placeholder="first name" v-model="firstName">
    <br><br>
    lastName : <input type="text" placeholder="first name" v-model="lastName">
    <br><br>
    heroName : <input type="text" placeholder="option Name" v-model="options.heroName">
</template>
<script>
import {reactive,toRefs,watch} from 'vue'
import _ from 'lodash'
export default {
    setup(){
        const state = reactive({
            firstName : '',
            lastName : '',
            options: {
                heroName: ''
            }
        })
        watch(()=>_.cloneDeep(state.options),(newVal,oldVal)=>{
            console.log('OLD value ', oldVal.heroName);
            console.log('NEW value ', newVal.heroName);
        })
        return {
            ...toRefs(state)
        }
    }
}
</script>

<style>

</style>