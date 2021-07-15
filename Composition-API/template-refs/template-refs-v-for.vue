<template>
    <div v-for="(item, i) in list" :ref="el => { if (el) divs[i] = el}">
        {{ item }}
    </div>
</template>
    
<script>
import { ref, reactive, onBeforeUpdate } from 'vue'

export default {
    
    setup() {
        const list = reactive([1, 2, 3])
        const divs = ref([])

        // make sure to reset the refs before each update
        onBeforeMount(() => {
            divs.value = []
        })

        return {
            list,
            divs
        }
    }
}
</script>