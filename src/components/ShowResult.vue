<template>
  <section>
      <h1>{{resultType}}</h1>
  </section>
</template>

<script>
// import axios from 'axios'
export default {
name:'ShowResult',
props:['resultType', 'searchTerm'],
data(){
    return{
       baseURI:'https://api.themoviedb.org/3/',
       apiKey:'94e21c35f1a4303de4bd1504d52ad385'
    }
},
computed:{
    // results(){
    //     let results = [];
    //     axios.get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=scrubs`).then(res => {
    //      results = [...res.data];
    //     })  
    //     return results
    // },
    type(){
        if (this.resultType === 'movies') return 'search/movie/';
        if (this.resultType === 'tv series') return 'search/tv/';
        else return ''
    }
},
methods:{
    
}

}
</script>

<style scoped lang="scss">
h1{
    text-transform: uppercase;
}
</style>