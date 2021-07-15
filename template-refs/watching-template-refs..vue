<template>
    <div ref="root">This is a root element</div>
</template>

<script>
import { ref, watchEffect } from 'vue'

export default {
    
    setup() {
        const root = ref(null)

        watchEffect(() => {
            // This effect runs before the DOM is updated, and consequently,
            // the template ref does not hold a reference to the element yet.

            console.log(root.value) // => null

        })

        return {
            root
        }

    }
}
</script>