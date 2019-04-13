<template>
  <div>
    <h1 class="title">How was your day?</h1>
    <a href="#" class="happy">
      <i class="far fa-laugh-beam"></i>Happy
    </a>
    <a href="#" class="sad">
      <i class="far fa-frown"></i>Sad
    </a>
    <a href="#" class="angry">
      <i class="far fa-angry"></i>Angry
    </a>
  </div>
</template>

<script>
export default {
  name: "Landing"
};
</script>

<style scoped>
div {
  display: flex;
  margin: auto;
  overflow: auto;
  flex-direction: column;
}

.title {
  margin-top: 100px;
  margin-bottom: 30px;
}

div a {
  font-size: 30px;
  text-decoration: none;
  text-align: center;
  margin-bottom: 50px;
  padding: 35px;
  color: #000;
}

div a.happy {
  background: #f4f142;
}

div a.sad {
  background: #429ef4;
}

div a.angry {
  background: #f44242;
}
</style>
