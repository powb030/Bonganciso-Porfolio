<template>
  <div class="card w-100 h-100 border-0 bg-secondary text-light">
    <img 
      :src="project.image" 
      class="card-img-top" 
      alt="..."
      style="height: 180px; object-fit: cover;"
    />
    <div class="card-body d-flex flex-column">
      <h5 class="card-title">{{ project.title }}</h5>
      <p class="card-text small flex-grow-1">{{ project.description }}</p>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
defineProps({
  project: {
    type: Object,
    required: true
  }
});
</script>