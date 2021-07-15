<script>

import { ref, reactive } from 'vue'

export default {
   props: {
       collectionName: String
   },
   
   setup(props) {
       const readersNumber = ref(0)
       const book = reactive({title: 'Vue 3 Wizardry'})

        // expose to template
       return {
           readersNumber,
           book
       }
   }
}
</script>