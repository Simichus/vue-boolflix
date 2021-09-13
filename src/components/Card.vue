<template>
  <div class="card">  
        <img class="poster" :src="showPoster(result)" alt="">
        <div class="info">
            <h2>{{result.title || result.name}}</h2>
            <h2>{{result.original_title || result.original_name}}</h2>
            <div>
                <span v-if="result.original_language != 'it' && result.original_language != 'en'">{{result.original_language}}</span>
                <img class="flag" v-else :src="showFlag(result)" alt="">
            </div>
            <div>
                <i v-for="(star, index) in stars(result.vote_average)" :key="index" class="fa-star" :class="star"></i>
            </div>
            <div class="overview">
                {{result.overview}}
            </div>
        </div>   
  </div>
</template>

<script>
export default {
name:'Card',
props:{
    result:Object,
},
methods:{
        showFlag(result){
            if (result.original_language == 'en') return require('@/assets/img/en.png')   
            else if (result.original_language == 'it') return require('@/assets/img/it.png')
            else return       
        },
        showPoster(result){
            if (result.poster_path){
                const basePath = 'https://image.tmdb.org/t/p';
            const posterSize = '/w500'
            return `${basePath}${posterSize}${result.poster_path}`
            }
            else return 'https://www.altavod.com/assets/images/poster-placeholder.png'
        },
        stars(vote){
            const stars = [];
            vote = Math.ceil(vote/2)
            for(let i = 0; i<5; i++){
                if (i<vote) stars.push('fas')
                else stars.push('far')
            }
            return stars
        }
        
    }
}
</script>

<style scoped lang="scss">
@import '../scss/_vars.scss';
.card{
    position: relative;
    width: 25%;
    padding: 50px;


    .poster{
        width: 100%;
        border-radius: 20px;
        
    }

    .flag{
        width: 50px;
        height: auto;
    }
}

.info{
    opacity: 0;
    text-align: center;
    margin: 50px;
    padding: 5px;
    color: $text-color;
    background-color: rgba($color: #000, $alpha: 0.5);
    border-radius: 20px;
    overflow-y: auto;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;

    &:hover{
        opacity: 1;
    }

    h2, div{
        margin: 10px 0;
    }

    .overview{
        font-size: 16px;
    }
}

</style>