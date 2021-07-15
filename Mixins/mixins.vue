<template>
    
</template>

<script>

export default {
    const myMixin = {
        created() {
            this.hello()
        },

        methods: {
            hello() {
                console.log('hello from mixin!')
            }
        },
    }

    // define an app that uses this mixin
    const app = Vue.createApp({
        mixins: [myMixin]
    })

    // => "hello from mixin!"
    app.mount('#mixins-basic')
}
</script>