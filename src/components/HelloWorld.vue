<script setup>
import ImageSlider from './ImageSlider.vue'

const colors = ['red', 'blue', 'green', 'yellow', 'purple', 'orange', 'gray']
</script>

<template>
  <div class="slider">
    <ImageSlider :num-items="colors.length">
      <div v-for="(color, index) in colors" :key="index" class="slide-image" :style="{ backgroundColor: color }">
        {{ color }}
      </div>
    </ImageSlider>
  </div>
</template>

<style scoped>
.slider {
  width: 100vw;
}
.slide-image {
  width: 70vw;
  height: 50vw;
}
</style>
