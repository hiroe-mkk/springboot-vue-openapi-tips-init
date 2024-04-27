<script setup lang="ts">
import { ref, onMounted } from 'vue';
import axios from 'axios';

const message = ref<string>('');

onMounted(async () => {
  try {
    const response = await axios.get('/api/hello')
    message.value = response.data
  } catch (error) {
    console.error('Error:', error)
  }
})
</script>

<template>
  <h2>{{ message }}</h2>

  <div class="card">
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
