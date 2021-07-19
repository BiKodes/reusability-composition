<template>
    
</template>

<script>
export default {
    const { h, resolveDynamicComponent } = Vue

    render() {
        const Component = resolveDynamicComponent(this.name)
        return h(Component)
    },
}
</script>