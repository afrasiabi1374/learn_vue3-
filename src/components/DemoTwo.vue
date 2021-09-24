<template>
  <div>
      <h1>name : {{name}} </h1>
      <h1>familly : {{familly}} </h1>
      <h1>university : {{university}} </h1>
  </div>
</template>

<script>
    import {toRefs,reactive} from 'vue'
    export default {
        setup() {
            const about = reactive({
                name : 'mohammad ali',
                familly : 'afrasibi',
                university : 'azad qazvin'
            })
            setTimeout(()=>{
                about.name = 'morterza'
                about.familly = 'safavi'
                about.university = 'shiraz'
            },3000)
            return toRefs (about)
            
        }
    }
</script>

<style>

</style>