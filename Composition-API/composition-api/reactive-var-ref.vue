<template>
    
</template>

<script>
import { fetchUserRepositories } from '@/api/repositories'
import { ref } from 'vue'

export default {
    
    setup(props) {
       const repositories = ref([])
       const getUserRepositories = async () => {
           repositories.value = await fetchUserRepositories(props.user)
       } 

       return {
           repositories,
           getUserRepositories
       }
    }
}
</script>