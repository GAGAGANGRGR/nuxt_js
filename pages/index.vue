<script setup>
import { ref } from 'vue';

import ustore from '@/stores'
const Text = ref('')

const handleSubmit = () => {
  navigateTo(`/search/${Text.value}`)
  console.log(Text.value);
  
//   storeing the data in to the store/indexedDB.js
  ustore.name=Text.value
  console.log('ustore.name',ustore.name);
};

</script>

<template>
  <div>
    <div class="search-container">
      <form @submit.prevent="handleSubmit" class="search-form">
        <input type="text" placeholder="Enter your name" v-model="Text" required class="search-input"/>
        <button type="submit" class="search-button">Search</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
.search-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
}

.search-form {
  background-color: #cac6c6;
  padding: 25px;
  border-radius: 10px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);
}

.search-input {
  width: 85%;
  padding: 20px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.search-button {
  margin: 5%;
  padding: 10px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}
</style>



