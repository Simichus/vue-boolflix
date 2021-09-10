<template>
  <div>
      <input type="text" v-model="searchMovie" placeholder="Cerca un film..." @keyup.enter="startResearch">
      <button @click="startResearch">Cerca</button>
  </div>
</template>

<script>
export default {
name: 'SearchMovie',
data(){
    return{
        searchMovie:''
    }
},
methods:{
    startResearch(){
        if (!this.searchMovie) return
        return this.$emit('startResearch', this.searchMovie)
    }
}
}
</script>

<style>

</style>