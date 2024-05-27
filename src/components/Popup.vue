<template>
    <div class="popup" v-if="profile">
      <div class="popup-content">
        <slot name="popup-title">
          <h2>{{ profile.name }}</h2>
        </slot>
        <slot name="popup-content">
          <img :src="profile.photo" alt="Profile Photo" />
          <p>{{ profile.description }}</p>
          <button @click="closePopup">Close</button>
        </slot>
      </div>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    profile: Object,
  });
  
  const emit = defineEmits(['close']);
  
  const closePopup = () => {
    emit('close');
  };
  </script>
  
  <style scoped>
  .popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-30%, -50%);
    z-index: 1000;
  }
  
  .popup-content {
    background: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    max-width: 60%; 
    max-height: 60%; 
    overflow: auto; 
  }
  
  .popup img {
    max-width: 100%;
    height: auto;
  }
  </style>
  