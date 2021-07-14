<template>
    
</template>

<script>
import useUserRepositories from '@/composables/useUserRepositories'
import useRepositoryNameSearch from '@/composables/useRepositoryNameSearch'
import { toRefs } from 'vue'

export default {
    components: { RepositoriesFilters, RepositoriesSortBy, RepositoriesList },
    props: {
        user: {
            type:String,
            required: true
        }
    },

    setup(props) {
        const { user } = toRefs(props)
        const { repositories, getUserRepositories } = useUserRepositories(user)

        const {
            searchQuery,
            repositoriesMatchingSearchQuery
        } = useRepositoryNameSearch(repositories)

        return {
            // Since we don’t really care about the unfiltered repositories
            // we can expose the filtered results under the `repositories` name
            repositories: repositoriesMatchingSearchQuery,
            getUserRepositories,
            searchQuery,
        }
    },

    data (){
        return {
            filters: {...}
        }
    },
    computed: {
        filteredRepositories (){},
    },
    methods: {
        updateFilters (){...}
    }
}
</script>