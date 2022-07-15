<template>
    <main>
  
  <!-- <h1>{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p> -->

  <!-- <button @click="increment">Count:
    {{ counter.count }}
  </button> -->

  <button @click="mutateDeeply">
    obj.nested.count: {{obj.nested.count }}
    
  </button>
       
  <p>  {{obj.nested.count }}</p>

  {{obj.arr.map(item => item)}}

  </main>
</template>

<script setup>
import { reactive, ref, nextTick } from 'vue'

// const counter = reactive({ count: 0 })
// const message = ref('Hello World!')

// function increment() {
//   counter.count++
//    nextTick(() => {
//     // access updated DOM
//   })

  const obj = reactive({
  nested: { count: 0 },
  arr: ['foo', 'bar']
})

function mutateDeeply() {
  // these will work as expected.
  obj.nested.count++
  obj.arr.push('baz')
}
</script>

<style  scoped>
main{
    background-color: gray;
    color:black;
    width: 100%;
    height: 30vh;
      display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>