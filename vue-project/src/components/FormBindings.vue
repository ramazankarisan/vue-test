<template>
    <main>
    <h1>Form Bindings</h1>
  <!-- <input :value="text" @input="onInput" placeholder="Type here">

 <input  :value="text"  @input="event => text = event.target.value">
The v-model directive helps us simplify the above to: -->

<!-- <input v-model="text"  placeholder="Type here its with v-model"> -->
  <!-- <p>{{ text }}</p> -->

<input v-model="message" placeholder="edit me" />
<p>Message is: {{ message }}</p>

<!-- for more info about form bindings >>> https://vuejs.org/guide/essentials/forms.html -->
    </main>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('')
const message = ref('')


function onInput(e) {
  text.value = e.target.value
}
</script>

<style  scoped>
main{
    background-color: rgb(185, 170, 170);
    color:black;
    width: 100%;
      display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
</style>