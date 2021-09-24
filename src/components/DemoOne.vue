<template>
  <div>

  </div>
</template>

<script>
    import {ref} from 'vue'
    export default {
        setup() {
            const name = ref('ali')
            setTimeout(()=>{
                name.value = 'behzad'
            },3000)
            return {
                name
            }
        }
    }
</script>

<style>

</style>