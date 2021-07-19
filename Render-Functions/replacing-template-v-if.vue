<template>
    <ul v-if="items.length">
        <li v-for="item in items">{{ item.name }}</li>
    </ul>
    <p v-else>No items found</p>
</template>

<script>
export default {
    props: ['items'],
    render() {
       if (this.items.length) {
           return h('ul', this.items.map((item) => {
               return h('li', item.name)
           }))
       } else {
           return h('p', 'No items found.')
       } 
    }
}
</script>