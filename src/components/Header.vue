<template>
  <header>
      <SearchMovie @startResearch="startResearch"/>
  </header>
</template>

<script>
import SearchMovie from '@/components/SearchMovie.vue'
export default {
name: 'Header',
components:{
    SearchMovie
},
methods:{
    startResearch(searchTerm){
        return this.$emit('startResearch', searchTerm)
    }
}
}
</script>

<style>

</style>