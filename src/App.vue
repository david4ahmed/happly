<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <!--<Contact/>-->
    <!--<ComfortZone/>-->
    <!--<ComplimentFriends/>-->
    <ComplimentUser/>
    <!--<ReflectBehavior/>-->
    <!--<RandomMedia/>-->
    <!--<Statistics/>-->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Contact from './components/Contact'
import ComfortZone from './components/ComfortZone'
import ComplimentFriends from './components/ComplimentFriends'
import ComplimentUser from './components/ComplimentUser'
import ReflectBehavior from './components/ReflectBehavior'
import RandomMedia from './components/RandomMedia'
import Statistics from './components/Statistics'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Contact,
    ComfortZone,
    ComplimentFriends,
    ComplimentUser,
    ReflectBehavior,
    Statistics
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
