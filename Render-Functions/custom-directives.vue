<template>
    
</template>

<script>
export default {

    const { h, resolveDirective, withDirectives } = Vue

    render() {
      const pin = resolveDirective('pin')
      
      return withDirectives(h('div'), [
          [pin, 200, 'top', { animate: true }]
      ])
    },
}
</script>