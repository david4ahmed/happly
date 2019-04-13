<template>
  <div class="container">
    <Header/>
    <Landing/>
  </div>
</template>

<script>
import Header from "./components/layout/Header.vue";
import Landing from "./components/Landing.vue";

export default {
  name: "app",
  components: {
    Header,
    Landing
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
