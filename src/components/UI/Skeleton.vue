<template>
    <div class="placeholder">
      &nbsp;
    </div>
  </template>
  
  <script setup>
  defineProps({
    height: {
      type: String,
    },
    width: {
      type: String,
    },
    borderRadius: {
      type: String,
    },
  });
  </script>
  
  <style scoped>
  @keyframes bgAnimate {
    0% {
      background-position: 50% 0;
    }
  
    100% {
      background-position: -150% 0;
    }
  }
  .placeholder {
    height: v-bind(height);
    width: v-bind(width);
    border-radius: v-bind(borderRadius);
    background-image: linear-gradient(
      to right,
      #3C3C3C 0%,
      #5f5f5f 40%,
      #444 50%,
      #3C3C3C 100%
    );
    background-size: 200% 100%;
    box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1),
      0 2px 4px -2px rgb(0 0 0 / 0.1);
    animation: bgAnimate 3.2s ease-in infinite;
  }
  </style>