<template>
  <div class="app">
    <carrossel
    @next="next"
    @prev="prev"
    >
      <carrosselslide v-for="(slide, index) in slides" 
      :key="slide" 
      :index="index"
      :visibleSlide="visibleSlide"
      :direction="direction"
      >
        <img :src="slide"/>
      </carrosselslide>
    </carrossel>
  </div>
</template>

<script>

import carrossel from "./components/Carrossel.vue"
import carrosselslide from "./components/CarrosselSlide.vue"

export default {
  data() {
    return {
      slides: [
      "https://picsum.photos/id/123/600/300",
      "https://picsum.photos/id/124/600/300",
      "https://picsum.photos/id/125/600/300",
      "https://picsum.photos/id/126/600/300",
      "https://picsum.photos/id/127/600/300",
      ],
      visibleSlide: 0,
      direction: '',
    }
  }, 
  computed: {
    slidesLen() {
      return this.slides.length;
    }
  },

  methods: {
    next() {
      if(this.visibleSlide >= this.slidesLen - 1) {
        this.visibleSlide = 0;
      }
      else {
        this.visibleSlide++;
      }
      this.direction = "left"
    }, 

    prev() {
      if(this.visibleSlide <= 0) {
        this.visibleSlide = this.slidesLen - 1;
      }
      else {
        this.visibleSlide--;
      }
      this.direction = "right"
    }
  },

  components: {
    carrossel,
    carrosselslide,
  }
}
</script>

<style>
  .app {
    display: flex;
    justify-content: center;
  }
</style>