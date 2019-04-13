<template>
  <div class="container">
    <Header/>
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <!--<Contact/>-->
    <!--<ComfortZone/>-->
    <!--<ComplimentFriends/>-->
    <!--<ComplimentUser/>-->
    <!--<ReflectBehavior/>-->
    <!--<RandomMedia/>-->
    <!--<Statistics/>-->
    <Landing/>
  </div>
</template>

<script>
import Header from "./components/layout/Header.vue";
import Contact from './components/Contact'
import ComfortZone from './components/ComfortZone'
import ComplimentFriends from './components/ComplimentFriends'
import ComplimentUser from './components/ComplimentUser'
import ReflectBehavior from './components/ReflectBehavior'
import RandomMedia from './components/RandomMedia'
import Statistics from './components/Statistics'
import Landing from "./components/Landing.vue";

export default {
  name: "app",
  components: {
    Header,
    Landing,
    Contact,
    ComfortZone,
    ComplimentFriends,
    ComplimentUser,
    ReflectBehavior,
    Statistics
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Open+Sans");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Open Sans", sans-serif;
  line-height: 1.6;
  background-image: url(../public/bckimg.jpg);
  background-position: center center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}

.container {
  max-width: 1100px;
  margin: auto;
  overflow: auto;
  padding: 0 2rem;
}
</style>
