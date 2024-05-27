<template>
    <div class="profile-list-container">
      <ul class="profile-list">
        <li v-for="profile in profiles" :key="profile.id">
          <button @click="selectProfile(profile)">
            <img :src="profile.photo" alt="Profile Photo" />
            <p>{{ profile.name }}</p>
          </button>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    profiles: Array,
  });
  
  const emit = defineEmits(['profileSelected']);
  
  const selectProfile = (profile) => {
    emit('profileSelected', profile);
  };
  </script>
  
  <style scoped>
  .profile-list-container {
    display: flex;
    justify-content: center; 
  }
  
  .profile-list {
    display: flex;
    flex-wrap: wrap; 
    list-style-type: none;
    padding: 0;
  }
  
  .profile-list li {
    margin: 10px;
  }
  
  .profile-list img {
    width: 150px;
    height: 150px;
    object-fit: cover;
  }
  </style>
  