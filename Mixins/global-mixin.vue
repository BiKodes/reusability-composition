<template>
    
</template>

<script>
export default {
    const app = vue.createApp({
        myOption: 'hello!'
    })

    // inject a handler for `myOption` custom option
    app.mixin({
        created() {
            const myOPtion = this.$options.myOption

            if (myOption) {
                console.log(myOption)
            }
        },
    })

    app.mount('#mixins-global') // "hello!"
}
</script>