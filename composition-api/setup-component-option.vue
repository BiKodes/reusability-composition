<template>
    
</template>

<script>
export default {
    components: { RepositoriesFilters, RepositoriesSortBy, RepositoriesList },
    props: {
        user: {
            type: String,
            required: true
        }
    },
    
    setup(props) {
      console.log(props) // {user: ..}

      return { } 
    }
}
</script>