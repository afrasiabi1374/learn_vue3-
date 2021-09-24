<template>
  <div>
      <input type="text" placeholder="fname" v-model="fName" />
      <input type="text" placeholder="lname" v-model="lName" />
      <input type="text" placeholder="hero-name" v-model="options.heroName" />

  </div>
</template>
<script>
    import {reactive, toRefs, watch} from 'vue'
    import _ from 'lodash'
    export default {
        setup() {
            const state = reactive({
                fName : '',
                lName : '',
                options : {
                    heroName : ''
                }
            })
            //halate aval chand taii
            // watch(()=>({
            //     ...state
            // }),(newValue, oldValue)=>{
            //     console.log('old name' , oldValue.fName);
            //     console.log('new name' , newValue.fName);
            //     console.log('old familly' , oldValue.lName);
            //     console.log('new familly' , newValue.lName);
            // })
            //halate 2
            // watch(()=>{
            //     return state.fName
            // },
            // (newValue,oldValue)=>{
            //     console.log("old : ",oldValue);
            //     console.log("new : ",newValue);
            // }
            // )

            watch(()=> _.cloneDeep(state.options) ,
            (newValue,oldValue)=>{
                console.log("old : ",oldValue);
                console.log("new : ",newValue);
            },{deep:true}
            )

            return {
                ...toRefs(state)
            }
        }
    }
</script>

<style>

</style>