<template>
    <p>Reaction time - {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
    export default{
       props: ['score'],
       data() {
        return {
            rank: null
        }
       },
       mounted(){
        if(this.score < 250){
            this.rank = 'Fast'
        }
        else if(this.rank < 400){
            this.rank = 'Faster'
        }
        else{
            this.rank = 'Slow...'
        }
       }
    }
</script>
<style>
    .rank{
        font-size: 25px;
        color: teal;
        font-weight: bold;
    }
</style>