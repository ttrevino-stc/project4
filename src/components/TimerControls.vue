<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['start', 'stop'])
</script>

<template>
  <button @click="emit('start')" id="startBtn">Start</button>
  <button @click="emit('stop')" id="stopBtn">Stop</button>

</template>