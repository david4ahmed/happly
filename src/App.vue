<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Contact/>
    <!--<ComfortZone/>-->
    <!--<Compliment/>-->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Contact from './components/Contact'
import ComfortZone from './components/ComfortZone'
import Compliment from './components/Compliment'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Contact,
    ComfortZone,
    Compliment
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
