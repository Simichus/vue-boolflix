<template>
  <section>
      <h1>{{title}}</h1>
      <div>
          <Card  v-for="result in resultArray" :key="result.id" :result="result"/>
      </div>
  </section>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
    components:{
        Card
    },
    name:'ShowResult',
    props:['resultArray', 'title'],
    
}
</script>

<style scoped lang="scss">
@import '../scss/_vars.scss';


section{

    h1{
        color: $main-text-color;
        text-align: center;
        font-size: 40px;
        text-transform: uppercase;
        margin-top: 25px;
    }

    div{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
}
</style>