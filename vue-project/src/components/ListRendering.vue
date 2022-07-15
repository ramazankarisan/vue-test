<template>
  <main>
   <h1>List Rendering</h1>
   <!-- We can use the v-for directive to render a list of elements based on a source array -->
   <!-- <ul>
  <li v-for="todo in todos" :key="todo.id">
    {{ todo.text }}
  </li>
</ul> -->
<li v-for="({message}, index) in items">
  	{{ parentMessage }} - {{ index }} - {{ message }}
	</li>


<form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>    
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  </main>
</template>

<script setup>
import { ref } from 'vue'

const parentMessage = ref('Parent Message')
const items = ref([{ message: 'Foo' }, { message: 'Bar' }])

// give each todo a unique id
let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn JavaScript' },
  { id: id++, text: 'Learn Vue' }
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>
<style scoped>
main {
  background-color: rgb(196, 227, 239);
  color: black;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
</style>
