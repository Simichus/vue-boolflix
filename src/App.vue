<template>
  <div id="app">
    <Header @startResearch="startResearch"/>
    <main>
    <ShowResult :result-array="movies" :title="moviesTitle"/>
    <ShowResult :result-array="series" :title="seriesTitle"/>
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import ShowResult from '@/components/ShowResult.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    ShowResult
  },
  data(){
    return{
      baseUri: 'https://api.themoviedb.org/3/',
      api: '94e21c35f1a4303de4bd1504d52ad385',
      movies:[],
      series:[],
      moviesTitle: '',
      seriesTitle: '',
    }
  },
  methods:{
    startResearch(query){
      this.getData(query, 'search/movie', 'movies')
      this.getData(query, 'search/tv', 'series')
      this.moviesTitle = 'Film'
      this.seriesTitle = 'Serie TV'
    },

    getData(query, endpoint, array){
      const params = {
        params:{
          api_key: this.api,
          language:'it-IT',
          query,         
        }
      }

      axios.get(`${this.baseUri}${endpoint}`, params).then(res => {
        this[array]= res.data.results
      })
    }
  }
}
</script>

<style lang="scss">
@import 'scss/style.scss';
main{
  margin: 20px 0;
}
</style>
