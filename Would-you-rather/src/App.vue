<script setup>
import WouldYouRather from './components/WouldYouRather.vue'
</script>

<template>
  <div id="app">
    <!-- Header -->


    <!-- WouldYouRather component -->
    <WouldYouRather
        question="Would you rather go to the beach or the mountains?"
        answer1="Beach"
        answer2="Mountains"
        @answer-selected="handleAnswerSelected"
    />


  </div>
</template>


<style scoped>
/* Scoped CSS for the parent component */
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f0f0;
}
</style>
