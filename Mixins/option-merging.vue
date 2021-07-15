<template>
    
</template>

<script>
export default {
    const myMixin = {
        data() {
            return {
                message: 'hello',
                foo: 'abc'
            }
        }
    }

    const app = Vue.createApp({
        mixins: [myMixin],

        data() {
            return {
                message: 'goodbye',
                bar: 'def'
            }
        },

        created() {
            console.log(this.$data) // => { message: "goodbye", foo: "abc", bar: "def" }
        },
    })
}
</script>