<template>
  <div id="app">
    <Header @startResearch="startResearch"/>
    <Main :searchTerm="searchTerm"/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
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
