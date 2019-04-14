<template>
  <div id="slider" class="slider" @mousemove="mouseMoving" @mouseleave="stopDrag">
    <div class="slider-cards" :style="`transform: translate3d(${cardsX}px,0,0)`">
      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Main/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Feel/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Spirit/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Mindful/>
      </div>

    </div>
  </div>
</template>

<script>
import tweenlite from 'gsap'

import Main from "./components/Main.vue";
import Feel from "./components/Feel.vue";
import Spirit from "./components/Spirit.vue";
import Mindful from "./components/Mindful.vue";
import Vue from 'vue'
import Vuetify from 'vuetify'

Vue.use(Vuetify);

export default {
  name: "app",
  components: {
    Main,
    Feel,
    Spirit,
    Mindful
  },
  data: function () {
    return {
      selectedIndex: 0,
      dragging: false,
      initialMouseX: 0,
      initialCardsX: 0,
      cardsX: 0
    }
  },
  methods: {
    startDrag (e) {
      this.dragging = true;
      this.initialMouseX = e.pageX;
      this.initialCardsX = this.cardsX;
    },
    stopDrag () {
      this.dragging = false;

      const cardWidth = 330;
      const nearestSlide = - Math.round(this.cardsX / cardWidth);
      this.selectedIndex = Math.min(Math.max(0, nearestSlide), 4 - 1);
      tweenlite.to(this, 0.3, {cardsX: -this.selectedIndex * cardWidth});
    },
    mouseMoving (e) {
      if(this.dragging) {
        const dragAmount = e.pageX - this.initialMouseX;
        const targetX = this.initialCardsX + dragAmount;
        this.cardsX = targetX;
      }
    }
  }
}
</script>

<style>
  html, body{
    font-family: 'Lato', sans-serif;
  }
  .slider {
    overflow: hidden;
    background-color: #1F1140;
    width: 360px;
    height: 685px;
  }

  .slider-cards {
    position: relative;
    width: 5000px;
    margin: 20px 30px;
    z-index: 1;
  }
  .slider-card {
    display: inline-block;
    background-color: #e6ffed;
    overflow: hidden;
    width: 300px;
    height: 649px;
    margin-right: 30px;
    border-radius: 12px;
    -webkit-box-shadow: 0px 60px 20px -20px rgba(0, 0, 0, 0.3);
    box-shadow: 0px 23px 14px -17px rgba(0, 0, 0, 0.3);
  }
</style>
