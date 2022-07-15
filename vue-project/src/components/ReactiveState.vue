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
<!-- 
Limitations of reactive()#
The reactive() API has two limitations:

It only works for object types (objects, arrays, and collection types such as Map and Set). It cannot hold primitive types such as string, number or boolean.

Since Vue's reactivity tracking works over property access, we must always keep the same reference to the reactive object. This means we can't easily "replace" a reactive object because the reactivity connection to the first reference is lost: -->

<!-- 
    let state = reactive({ count: 0 })

// the above reference ({ count: 0 }) is no longer being tracked (reactivity connection is lost!)
state = reactive({ count: 1 }) -->


<!-- It also means that when we assign or destructure a reactive object's property into local variables, or when we pass that property into a function, we will lose the reactivity connection:

const state = reactive({ count: 0 })

// n is a local variable that is disconnected
// from state.count.

let n = state.count
// does not affect original state
n++

// count is also disconnected from state.count.
let { count } = state
// does not affect original state
count++

// the function receives a plain number and
// won't be able to track changes to state.count
callSomeFunction(state.count) -->
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