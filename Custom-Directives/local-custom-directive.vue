<template>
    <input v-focus />
</template>

<script>
export default {
   directives: {
       focus: {
       //directive definition
       mounted(el) {
           el.focus()
       },
    } 
   }
}
</script>