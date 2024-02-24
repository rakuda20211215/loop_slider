<script setup>
import { ref } from 'vue'
import ImageSlider from './ImageSlider.vue'

const goToNextPage = ref(true)

const colors = ['red', 'blue', 'green', 'yellow', 'purple', 'orange', 'gray']

const clickNextPage = (e) => {
  if (!goToNextPage.value) e.preventDefault()
}
</script>

<template>
  <div class="slider">
    <ImageSlider :num-items="colors.length" v-model:goToNextPage="goToNextPage">
      <div v-for="(color, index) in colors" :key="index" class="slide-image" :style="{ backgroundColor: color }">
        <a :href="`https://www.google.com/search?q=${color}`" @click="clickNextPage" draggable="false">{{ color }}</a>
      </div>
    </ImageSlider>
  </div>
</template>

<style scoped>
.slider {
  width: 100vw;
}
.slide-image {
  margin: 2vw;
}
.slide-image a {
  font-size: 50px;
  color: white;
  width: 65vw;
  height: 50vw;
}
</style>
