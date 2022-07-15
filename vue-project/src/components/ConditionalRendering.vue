<template>
  <main>
    <h1>Conditional Rendering</h1>
    <!-- v-if# -->
<!-- The directive v-if is used to conditionally render a block. The block will only be rendered if the directive's expression returns a truthy value. -->
<button @click="awesome = !awesome">Toggle</button>

<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>

<!-- v-if on <template></template> is also doable -->

<!-- v-else-if  there is also this -->

  </main>
</template>

<script setup>
import { ref } from 'vue';

const awesome = ref(true)
</script>
<style scoped>
main {
  background-color: rgb(239, 196, 196);
  color: black;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
</style>
