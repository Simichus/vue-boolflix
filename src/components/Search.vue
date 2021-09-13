<template>
  <div>
      <input type="text" v-model="searchTerm" placeholder="Cerca un film..." @keyup.enter="startResearch">
      <button @click="startResearch">Cerca</button>
  </div>
</template>

<script>
export default {
name: 'Search',
data(){
    return{
        searchTerm:''
    }
},
methods:{
    startResearch(){
        if (!this.searchTerm) return
        return this.$emit('startResearch', this.searchTerm)
    }
}
}
</script>

<style>

</style>