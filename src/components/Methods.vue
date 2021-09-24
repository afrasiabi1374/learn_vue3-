<template>
  <div>
      <h2>
          name : {{name}}
          <br>
          last name : {{lastName}}
          <br>
          university : {{uniName}}
          <br>
          city of university : {{uniCity}}
      </h2>
      <button @click="chenger">change sth</button>
  </div>
</template>

<script>
import {toRefs,reactive} from 'vue'

export default {
    name : 'Methods',
    setup() {
        const aboutSelf = reactive({
            name : 'mohammadAli',
            lastName : "afrasiabi"
        }) 
        const aboutUni = reactive({
            uniName : 'raja',
            uniCity : 'qazvin'
        })
        function chenger() {
            aboutSelf.name = "hadi"
            aboutSelf.lastName = "zare"
            aboutUni.uniName = "amir kabir"
            aboutUni.uniCity = "Tehran"

        }
        return {
            ...toRefs(aboutSelf),
            ...toRefs(aboutUni),
            chenger
        }
    }
}
</script>

<style>

</style>