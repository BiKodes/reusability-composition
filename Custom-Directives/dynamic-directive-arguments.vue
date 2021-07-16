<template>
    <div id="dynamicexample">
        <h3>Scroll down inside this section</h3>
        <p v-pin:[direction]="200">I am pinned onto the page at 200px to the left.</p>
    </div>
</template>

<script>
export default {
    
    const app = Vue.createApp({
        data() {
            return {
                direction: 'right'
            }
        },
    })

    app.directive('pin', {
        mounted(el, binding) {
            el.style.position = 'fixed'
            // binding.arg is an argument we pass to directive
            const s = binding.arg || 'top'
            el.style[s] = binding.value + 'px'
        }
    })

    app.mount('#dynamic-arguments-example')
}
</script>