<template>
    
</template>

<script>
export default {
    const myMixin = {
        created() {
            console.log('mixin hook called')
        },
    },

    const app = Vue.createApp({
        mixins: [myMixin],
        created() {
            console.log('component hook called')
        }
    })
}

// => "mixin hook called"
// => "component hook called"
</script>