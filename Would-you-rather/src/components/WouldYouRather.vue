<script setup>
// Importing necessary functions from Vue
import { ref } from 'vue'

// Define props to receive question and answers from parent component
defineProps({
  question: String,
  answer1: String,
  answer2: String
})

// Define emits to send events to parent component
const emit = defineEmits([
  'answer-selected'
])

// Define a reactive variable to hold the user's choice
const choice = ref('')

// Function to emit event when choice is made
function choiceMade() {
  emit('answer-selected', choice.value)
}
</script>

<template>

  <div id="wyr">
    <!-- Heading for the app -->
    <h2>Would you rather?</h2>
    <h3>Make your choice!</h3>

    <!-- Displaying the question -->
    <div id="question">
      {{ question }}
    </div>

    <!-- Form to select answers -->
    <div id="answers">
      <!-- Radio buttons for answer 1 -->
      <input type="radio" id="answer-1" v-model="choice" :value="answer1" @change="choiceMade">
      <label for="answer-1"> {{ answer1 }}</label>

      <!-- Radio buttons for answer 2 -->
      <input type="radio" id="answer-2" v-model="choice" :value="answer2" @change="choiceMade">
      <label for="answer-2"> {{ answer2 }}</label>
    </div>
  </div>
</template>

<style scoped>
/* Scoped CSS to apply styles only to this component */
#wyr {
  background-color: hotpink;
  padding: 20px;
}

#answers {
  padding: 10px;
}
</style>

