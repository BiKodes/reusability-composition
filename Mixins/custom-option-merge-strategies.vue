<template>
    
</template>

<script>
export default {
    const app = Vue.createApp({
        custom: 'hello!'
    })

    app.config.optionMergeStrategies.custom = (toVal, fromVal) => {
        console.log(fromVal, toVal)
        // => "goodbye!", undefined
        // => "hello", "goodbye!"
        return fromVal || toVal
    }

    app.mixin({
        custom: 'goodbye!',
        created() {
            console.log(this.$options.custom)
        },
    })
}
</script>