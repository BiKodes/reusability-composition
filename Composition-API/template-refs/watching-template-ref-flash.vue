<template>
    <div ref="root"> This is a root element</div>
</template>

<script>
import { ref, watchEffect } from 'vue'

export default {
    
    setup() {
        const root = ref(null)

        watchEffect(() => {
            console.log(root.value) // => <div>This is a root element</div>
        },
        
        {
            flush: 'post'
        })

        return {
            root
        }
    }
}
</script>