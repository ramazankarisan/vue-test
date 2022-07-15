<template>
<!-- directive documentation -->
<!-- https://vuejs.org/guide/essentials/template-syntax.html#directives -->

<!-- Mustaches (double curly brackets) cannot be used inside HTML attributes. Instead, use a v-bind directive: -->
<!-- <div v-bind:id="dynamicId"></div> -->

<!-- Because v-bind is so commonly used, it has a dedicated shorthand syntax:
<div :id="dynamicId"></div> -->

<!-- Expressions Only#
Each binding can only contain one single expression. An expression is a piece of code that can evaluate to a value. A simple check is whether it can be used after return.

Therefore, the following will NOT work:

 this is a statement, not an expression: -->
<!-- {{ var a = 1 }} -->

<!-- flow control won't work either, use ternary expressions -->
<!-- {{ if (ok) { return message } }} --> 


    <main>
    <h1 :class="headingClass">this should be red</h1>
    <!-- Inline Handlers -->
    <!-- for more info about events ->> https://vuejs.org/guide/essentials/event-handling.html#listening-to-events -->
    <button @click="increment">Count: {{ count }}</button>

    </main>
</template>

<script setup>
import { ref } from 'vue';

const headingClass = ref("classDiv")

const count = ref(0)
function increment() {
  // update component state
  count.value++
}
</script>

<style  scoped>
main{
    background-color: rgb(142, 129, 129);
    color:black;
    width: 100%;
    height: 30vh;
      display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
.classDiv{
    color:red;
}
</style>