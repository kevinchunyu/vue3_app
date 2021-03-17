<template>
  <div class="title">
    <div class="center">
      <h2>Filter LearnVue Articles</h2>
      <input
        type='text'
        placeholder='Filter Search'
        v-model='query'
      />
      <br>
      <button @click ='reset'> Reset</button>
      <search-results :query='query'/>
    </div>
  </div>
</template>

<script>
  import { ref } from 'vue'
  import SearchResults from './SearchResults.vue'
  export default {
    components: {
      SearchResults
    },
    // setup function is sused when component is created and where we can define REACTIVE DATA, COMPUTED PROPERTIES, METHODS, THAT WE WANT
    // OUR COMPONENTS TO USE
    setup() {
      const query = ref('')
      const reset = (evt) => {
        console.log(evt)
        query.value = '' // clearing the query typed in by the user
      }
      return {
        reset,
        query
      }
    }
  }
</script>

<style>
  input[type='text'] {
    margin-bottom: 20px;
    padding: 10px;
  }
  
  .title{
    display:flex;
    justify-content: center;
  }
  
</style>