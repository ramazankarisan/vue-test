<template>
  <main>
   <h1>Lifecycle and Template Ref</h1>
  
  <!-- for mor info >>> https://vuejs.org/guide/essentials/lifecycle.html -->
  <p ref="p">hello</p>
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const p = ref(null)

onMounted(() => {
  p.value.textContent = 'mounted! it was "hello" before'
})
</script>
<style scoped>
main {
  background-color: rgb(139, 125, 154);
  color: black;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
</style>
