<template>
    <input v-focus/>
</template>

<script>
export default {
    const app = Vue.createApp({})

    app.directive('focus', {
        // When the bound element is mounted into the DOM
        mounted(el) {
            // Focus the element
            el.focus()
        },
    })
}
</script>