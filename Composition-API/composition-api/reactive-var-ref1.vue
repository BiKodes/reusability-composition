<template>
    
</template>

<script>
import { fetchUserRepositories } from '@/api/respositories'
import { ref } from 'vue'

export default {
  components: {RepositoriesFilters, RepositoriesSortBy, RepositoriesList },
  props: {
      user: {
          type: String,
          required: true
      }
  },

  setup(props) {
     const repositories = ref([])
     const getUserRepositories = async () => {
         repositories.value = await fetchUserRepositories(props.user)
     } 

     return {
         repositories,
         getUserRepositories
     }
  },

  data () {
      return {
          filters: {...},
          searchQuery: ''
      }
  },
  computed: {
      filteredRepositories () {...},
      repositoriesMatchingSearchQuery () {...},
  },
  watch: {
      user: 'getUserRepositories'
  },

  methods: {
      updateFilters () {...}
  },
  mounted() {
      this.getUserRepositories()
  },
  
}
</script>