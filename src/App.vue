<template>
  <div id="app">
  <h1>{{message}}</h1>
  <p>My first App!</p>
  <circle-slider v-model="val1"></circle-slider>
  <div>{{ val1 }}</div>
<router-view/>
  </div>
</template>

<script>

import Hello from './components/HelloWorld'

export default {
  name: 'App',
  data(){
    return{
      message : "Climbing Grade Converter!"
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
