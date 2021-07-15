<template>
    
</template>

<script>
export default {
    const myMixin = {
        methods: {
            foo() {
                console.log('foo')
            },
            conflicting() {
                console.log('from mixin')
            }
        }
    }

    const app = Vue.createApp({
        mixins: [myMixin]
        methods: {
            bar() {
                console.log('bar')
            },

            conflicting(){
                console.log('from self')
            }
        },
    })

    const vm = app.mount('#mixins-basic')
}
</script>