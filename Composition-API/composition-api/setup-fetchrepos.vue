<template>
    
</template>

<script>
import { fetchUserRepositories } from '@/api/repositories'
export default {
    // inside our component

    setup(props) {
        let repositories = []
        const getUserRepositories = async () => {
            repositories = await fetchUserRepositories(props.user)
        }

        return {
            repositories,
            // functions returned behave the same as methods
            getUserRepositories 
        }
    }
}
</script>