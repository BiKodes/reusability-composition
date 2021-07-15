<template>
    
</template>
<script>
import { h, ref, reactive } from 'vue'

export default {
    setup(props) {
        
        const readersNumber = ref(0)
        const book = reactive({ title: 'Vue 3 Ninja'})

        return () => h('div', [readersNumber.value, book.title])
    }
}
</script>