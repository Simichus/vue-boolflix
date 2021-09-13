<template>
  <header>
      <h1>Boolflix</h1>
      <Search @startResearch="startResearch"/>
  </header>
</template>

<script>
import Search from '@/components/Search.vue'
export default {
name: 'Header',
components:{
    Search
},
methods:{
    startResearch(searchTerm){
        return this.$emit('startResearch', searchTerm)
    }
}
}
</script>

<style scoped lang="scss">
@import '../scss/_vars.scss';

header{
    display: flex;
    background-color: $secondary-color;
    justify-content: space-between;
    align-items: center;
    padding: 20px 50px;

    h1{
        color:$main-text-color
    }
}
</style>