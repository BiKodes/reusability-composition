<template>
    
</template>
<script>
import { fetchUserRepositories  } from '@/api/repositories'
import { ref, onMounted, watch, toRefs } from 'vue'

export default {
   setup(props) {
       // using `toRefs` to create a Reactive Reference to the `user` property of props
       const { user } = toRefs(props)

       const repositories = ref([])
       const getUserRepositories = async () => {
           // update `props.user` to `user.value` to access the Reference value
           repositories.value = await fetchUserRepositories(user.value)
       }

       onMounted(getUserRepositories)

       // set a watcher on the Reactive Reference to user prop
       watch(user, getUserRepositories)

       return {
           repositories,
           getUserRepositories
       }
   } 
}
</script>