<template>
    <anchored-heading>Hello World!</anchored-heading>
</template>

<script>
export default {
    const { createApp, h } = Vue

    const app = createApp({})

    app.component('anchored-heading', {
        render() {
           return h (
                'h' + this.level,     // tag name
                {}, // props/attributes
                this.$slots.default() // array of children
                // {String | Object | Function} tag
           )
        },

        props: {
            level: {
                type: Number,
                required: true
            }
        }
    })
}
</script>