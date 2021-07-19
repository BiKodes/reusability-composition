<template>
    
</template>

<script>
export default {
    const { createApp, h } = Vue
    
    const app = ccreateApp({})

    /** Recursively get text from children nodes */
    function getChildrenTextContent(children) {
        return children
            .map(node => {
                return typeof node.children === 'string'
                    ? node.children
                    : Array.isArray(node.children)
                    ? getChildrenTextContent(node.children)
                    : ''
            })
            .join('')
    }

    app.component('anchored-heading', {
        render() {
            // create kebab-case id from the text contents of the children
            const headingId = getChildrenTextContent(this.$slots.default())
                .toLowerCase()
                .replace(/\W+/g, '-')      // replace non-word characters with dash 
                .replace(/(^-|-$)/g, '')   // remove leading and trailing dashes

            return h('h' + this.level, [
                h(
                    'a',
                    {
                        name: headingId,
                        href: '#' + headingId
                    },
                    this.$slots.default()
                )
            ])
 
        },

        props: {
            level: {
                type: Number,
                required: true
            }
        }
    })
}
</script>