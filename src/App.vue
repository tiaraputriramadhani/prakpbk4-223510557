<template>
  <div>
  <Header />
  <p class="main-sentence">cintai produk lokal.<br> jeno dari malang.<br>mark dari palembang.</p>
  <ProfileList :profiles="profiles" @profileSelected="handleProfileSelected" />
  <Popup v-if="selectedProfile" :profile="selectedProfile" @close="selectedProfile = null" />
  <Footer />
</div>
</template>

<script setup>
import { ref } from 'vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Popup from './components/Popup.vue';
import ProfileList from './components/ProfileList.vue';

const profiles = ref([
  {
    id: 1,
    name: 'Lee Jeno',
    photo: 'public/images/hubby1.jpeg',
    description: ' Mi sto innamorando di te.'
  },
  {
    id: 2,
    name: 'Mark Lee',
    photo: 'public/images/hubby2.jpeg',
    description: 'To the world you may be one person, but to one person you are the world.'
  }
]);

const selectedProfile = ref(null);

const handleProfileSelected = (profile) => {
  selectedProfile.value = profile;
};
</script>

<style scoped>
.main-sentence {
  text-align: center;
  font-size: 18px;
  margin-bottom: 20px;
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>