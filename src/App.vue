<template>
  <div id="app">
    <Header @startResearch="startResearch"/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  },
  data(){
    return{
      searchTerm:''
    }
  },
  methods:{
    startResearch(searchTerm){
      this.searchTerm = searchTerm
    }
  }
}
</script>

<style lang="scss">

</style>
