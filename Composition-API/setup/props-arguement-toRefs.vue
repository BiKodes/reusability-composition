<script>
import { toRefs } from 'vue'

export default {
    setup(props) {
        const {title} = toRefs(props)
        console.log(title.value)
    }
}
</script>