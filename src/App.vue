<template>
  <div id="slider" class="slider" v-bind:class="getCurrentComponentId()" @mousemove="mouseMoving" @mouseleave="stopDrag">
    <div class="left_tap" @click="goLeft"></div>

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

       <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Callenge/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <OnlineCallenge/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <OfflineCallenge/>
      </div>

      <div @mousedown="startDrag"
           @mouseup="stopDrag"
           class="slider-card">
        <Contract/>
      </div>

    </div>

    <div class="right_tap" @click="goRight"></div>
  </div>
</template>

<script>
import tweenlite from 'gsap'

import Main from "./components/Main.vue";
import Feel from "./components/Feel.vue";
import Spirit from "./components/Spirit.vue";
import Mindful from "./components/Mindful.vue";
import Callenge from "./components/Callenge.vue";
import OnlineCallenge from "./components/OnlineCallenge.vue";
import OfflineCallenge from "./components/OfflineCallenge.vue";
import Contract from "./components/Contract.vue";
import Vue from 'vue'
import Vuetify from 'vuetify'

Vue.use(Vuetify);

export default {
  name: "app",
  components: {
    Main,
    Feel,
    Spirit,
    Mindful,
    Callenge,
    OnlineCallenge,
    OfflineCallenge,
    Contract
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
      this.selectedIndex = Math.min(Math.max(0, nearestSlide), 8 - 1);
      tweenlite.to(this, 0.3, {cardsX: -this.selectedIndex * cardWidth});
    },
    mouseMoving (e) {
      if(this.dragging) {
        const dragAmount = e.pageX - this.initialMouseX;
        const targetX = this.initialCardsX + dragAmount;
        this.cardsX = targetX;
      }
    },
    getCurrentComponentId(){
      switch (this.selectedIndex) {
        case 0: return "Main";
        case 1: return "Feel";
        case 2: return "Spirit";
        case 3: return "Mindful";
        case 4: case 5: case 6: return "Challenge";
      }
    },
    goLeft(){
      const cardWidth = 330;
      this.selectedIndex = Math.max(this.selectedIndex-1, 0);
      tweenlite.to(this, 0.3, {cardsX: -this.selectedIndex * cardWidth});
    },
    goRight(){
      const cardWidth = 330;
      this.selectedIndex = Math.min(this.selectedIndex+1, 8 - 1);
      tweenlite.to(this, 0.3, {cardsX: -this.selectedIndex * cardWidth});
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

  .Main {
    background-color: rgba(0, 255, 208, 0.06);
  }
  .Feel {
    background-color: rgba(116, 104, 93, 0.26);
  }
  .Spirit {
    background-color: rgba(0, 44, 180, 0.3);
  }
  .Mindful {
    background-color: rgba(251, 176, 1, 0.1);
  }
  .Challenge {
    background-color: rgba(114, 181, 118, 0.15);
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

  .left_tap{
    width: 30px;
    height: 200px;
    position: fixed;
    top: calc(50% - 100px);
    z-index: 99999;
  }
  .right_tap{
    width: 30px;
    height: 200px;
    position: fixed;
    top: calc(50% - 100px);
    left: 330px;
    z-index: 99999;
  }
</style>
