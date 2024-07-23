<template>
    <div>
      <h2 class="text-xl font-semibold mb-2">
        {{ foodName }}
        <img src="https://www.w3schools.com/vue/img_quality.svg" v-show="isFavorite" class="h-6 float-right">
      </h2>
      <p class="mb-2">{{ foodDesc }}</p>
      <button @click="toggleFavorite" class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-700">
        Favorite
      </button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['foodName', 'foodDesc', 'isFavorite'],
    methods: {
      toggleFavorite() {
        this.$emit('toggle-favorite', this.foodName);
      }
    }
  }
  </script>
  