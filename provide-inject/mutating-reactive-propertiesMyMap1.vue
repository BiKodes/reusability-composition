<template>
    
</template>

<script>
import { provide, reactive, ref } from 'vue'
import MyMaker from './using-injectMyMarker.vue'

export default {
    components: {
        MyMaker
    },

    setup() {
        const location = ref('North Pole')
        const geolocation = reactive({
            longitude: 90,
            latitude: 135
        })

        const updateLocation = () => {
            location.value = 'South Pole'
        }

        provide('location', location)
        provide('geolocation', geolocation)
        provide('updateLocation', updateLocation)
    }
}
</script>