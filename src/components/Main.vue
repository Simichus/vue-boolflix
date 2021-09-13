<template>
  <section>
      <ShowResult result-type="movies" :search-term="searchTerm"/>
      <ShowResult result-type="tv series" :search-term="searchTerm"/>
  </section>
</template>

<script>
import ShowResult from '@/components/ShowResult.vue'
export default {
name:'Main',
components:{
    ShowResult
},
props:['searchTerm'],
}
</script>

<style>

</style>