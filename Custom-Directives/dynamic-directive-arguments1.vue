<template>
    <div id="dynamicexample">
        <h2>Scroll down the page</h2>
        <input type="range" min="0" max="500" v-model="pinPadding">
        <p v-pin:[direction]="pinPadding">
            Stick me {{ pinPadding + 'px' }} from the {{ direction || 'top' }} of the page
        </p>
    </div>
</template>

<script>
export default {
    const app = Vue.createApp({
        data() {
            return {
                direction: 'right'
                pinPadding: 200
            }
        },
    })

    app.directive('pin', {
        mounted(el, binding) {
           el.style.position = 'fixed'
           const s = binding.arg || 'top'
           el.style[s] = binding.value + 'pk' 
        },

        updated(el, binding) {
           const s = binding.arg || 'top'
           el.style[s] = binding.value + 'px' 
        },
    })
}
</script>