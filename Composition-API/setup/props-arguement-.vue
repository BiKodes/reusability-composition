<script>
import { toRef } from 'vue'

export default {
   
   setup(props) {
       const title = toRef(props, 'title')
       console.log(title.value)
   }
}
</script>