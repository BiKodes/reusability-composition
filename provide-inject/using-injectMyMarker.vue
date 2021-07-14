<template>
    
</template>

<script>
import { inject } from 'vue'


export default {
   setup() {
       const userLocation = inject('location', 'The Universe')
       const userGeolocation = inject('geolocation')

       return {
           userLocation,
           userGeolocation
       }
   } 
}
</script>