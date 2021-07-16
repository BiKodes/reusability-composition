<template>
    <body>
        <div style="position: relative">
            <h3>Tooltips with Vue 3 Teleport</h3>
            <div>
                <modal-button></modal-button>
            </div>
        </div>
    </body>
</template>

<script>

export default {
   app.component('modal-button', {
       template:`
            <button @click="modalOpen = true">
                Open full screen modal! (Watch teleport)
            </button>

            <teleport to="body">
                <div v-if="modalOpen" class="modal">
                    <div>
                        I'm a teleported modal! 
                        (My parent is "body") 
                        <button @click="modalOpen = false">
                            Close
                        <button>
                    </div>
                </div>
            </teleport>
            `
            data() {
                return {
                    modalOpen: false
                }
            }
   }) 
}
</script>