<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps(['timeInput'])
const emit = defineEmits(['update:timeInput'])
</script>

<template>
  <input 
    type="number" 
    placeholder="Enter seconds" 
    min="1" 
    max="60" 
    :value="props.timeInput"
    @input="emit('update:timeInput', $event.target.value)"/>

</template>