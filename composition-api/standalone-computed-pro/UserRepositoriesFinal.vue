<template>
    
</template>

<script>
import { oRefs } from 'vue'
import useUserRepositories from '@/composables/useUserRepositories'
import useUserRepositoryNameSearch from '@/composables/useRepositoryNameSearch'
import useRepositoryFilters from '@/composables/useRepositoryFilters'

export default {
    components: { RepositoriesFilters, RepositoriesSortBy, RepositoriesList },
    props: {
        user: {
            type: String,
            required: true
        }
    },

    setup(props) {
        const { user } = toRefs(props)

        const { repositories, getUserRepositories } = useUserRepositories(user)

        const {
            filters,
            updateFilters,
            filteredRepositories
        } = useRepositoryFilters(repositoriesMatchingSearchQuery)

        return {
            // Since we don’t really care about the unfiltered repositories
            // we can expose the end results under the `repositories` name
            repositories: filteredRepositories,
            getUserRepositories,
            searchQuery,
            filters,
            updateFilters
        }
    }
}
</script>