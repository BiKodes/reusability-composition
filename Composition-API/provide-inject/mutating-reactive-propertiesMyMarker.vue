<script>
import { inject } from 'vue'

export default {
    
    setup() {
        const userLocation = inject('location', 'The Universe')
        const userGeolocation = inject('geolocation')
        const updateLocation = inject('updateLocation')

        return {
            userLocation,
            userGeolocation,
            updateLocation
        }
    }
}
</script>