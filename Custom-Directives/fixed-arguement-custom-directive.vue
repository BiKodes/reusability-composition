<template>
    <div id="dynamic-arguments-example" class="demo">
       <p>Scroll down the page</p>
       <p v-pin="200">Stick me 200px from the top of the page</p>
    </div>
</template>

<script>
export default {
   const app = Vue.createApp({})
   
   app.directive('pin', {
      mounted(el, binding) {
         el.style.position = 'fixed'
         // binding.value is the value we pass to directive - in this case, it's 200
         el.style.top = binding.value + 'px'
      },
   })

   app.mount('#dynamic-arguments-example')
}
</script>