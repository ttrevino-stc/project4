<script setup>
import { defineProps } from 'vue';

defineProps(['formattedTime']);
</script>

<template>
  <h2 id="timerDisplay">{{ formattedTime }}</h2>
  
</template>