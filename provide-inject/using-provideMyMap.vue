<template>
    <MyMaker />
</template>

<script>
import { provide } from 'vue'
import MyMaker from './using-injectMyMarker.vue'

export default {
    components: {
        MyMaker
    },

    setup() {
        provide('location', 'North Pole')
        provide('geolocation', {
            longitude: 90,
            latitude: 135
        })
    }
}
</script>