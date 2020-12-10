<template>
    <div class = "title">
      <h1>{{ title }}</h1>
    </div>
    <div class = "btn">
    <button @click = "startHandler">Go</button>
    </div>
    <Playground :delay = "delay" v-if = "isPlaying"/>
</template>

<script>
  import Playground from "./components/Playground"
  export default{
    name : "App",
    components : {
      Playground
    },
    data(){
      return{
        title : "Reaction Timer",
        isPlaying : false,
        delay : null
      }
    },
    methods : {
      startHandler(){
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
      }
    }
  }
</script>

<style scoped>
  .title{
    text-align: center;
    font-family: 'Nerko One', cursive;
    color: #35495e ;
  }

  .btn{
    text-align: center;
  }

  .btn button{
    width: 60px;
    height: 30px;
    cursor: pointer;
  }
</style>
