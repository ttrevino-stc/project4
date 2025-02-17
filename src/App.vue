<script setup>
import {ref, computed} from 'vue'

const timeInput = ref(null)
const timeLeft = ref(0)
let countdown = null

const formattedTime = computed(() => {
  return `00:${timeLeft.value < 10 ? '0' : ''}${timeLeft.value}`
})

const startCountdown = () => {
  stopCountdown()

  if (isNaN(timeInput.value) || timeInput.value < 1 || timeInput.value > 60) {
    alert("Please enter a number between 1 and 60")
    return
  }

  timeLeft.value = timeInput.value

  countdown = setInterval(() => {
    if (timeLeft.value <= 0) {
      stopCountdown();
      alert("Time's up!");
    } else {
      timeLeft.value--;
    }
  }, 1000)
}

const stopCountdown = () => {
  clearInterval(countdown)
  countdown = null
  timeLeft.value = 0
}
</script>


<template>
  <div class="container">
    <h1>Countdown Timer</h1>
    <input type="number" placeholder="Enter seconds" min="1" max="60" v-model.number="timeInput"/>

    <button @click="startCountdown" id="startBtn">Start</button>
    <button @click="stopCountdown" id="stopBtn">Stop</button>

    <h2 id="timerDisplay">{{ formattedTime }}</h2>

  </div>
</template>
