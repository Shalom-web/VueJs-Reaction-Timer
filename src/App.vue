<template>

  <h1>Welcome To Reaction Timer Game</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>

</template>


<script>
  import Block from './components/Block.vue'
  import Results from './components/Results.vue'


  export default{
    name: 'App',
    components: { Block, Results },

    data(){
      return{
        isPlaying: false,
        delay: null,
        score: null,
        showResults: false
      }
    },
    methods: {
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true

    }
  }
}
</script>

<style>
   button{
    background: teal;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 5px;
    font-size: 30px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
   }
   button[disabled]{
    opacity: 0.2;
    cursor: not-allowed;
   }
   h1{
    font-size: 50px;
    font-weight: 900;
    color: rgb(0, 188, 250);
   }
</style>

