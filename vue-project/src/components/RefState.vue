<template>
    <main>
    <h1> count:{{count}}</h1>
    <h1> foo:{{foo}}</h1>
    <h1> bar:{{bar}}</h1>
    </main>
</template>

<script setup>
import { ref } from 'vue'

const count = ref(0)

console.log(count) // { value: 0 }
console.log(count.value) // 0

count.value++
console.log(count.value) // 1

// Refs can also be passed into functions or destructured from plain objects without losing reactivity:
const obj = {
  foo: ref(1),
  bar: ref(2)
}

// the function receives a ref
// it needs to access the value via .value but it
// will retain the reactivity connection
// callSomeFunction(obj.foo)

// still reactive
const { foo, bar } = obj

// When refs are accessed as top-level properties in the template, they are automatically "unwrapped" so there is no need to use .value
</script>

<style  scoped>
main{
    background-color: rgb(205, 203, 203);
    color:black;
    width: 100%;
    height: 30vh;
      display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;

}
</style>