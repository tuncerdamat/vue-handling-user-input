<script setup>
import { ref } from 'vue'

const message = ref('Hello World!')

function reverseMessage() {
  // Access/mutate the value of a ref via
  // its .value property.
  message.value = message.value.split('').reverse().join('')
}

function notify() {
  alert('Navigation was prevented.')
}
</script>

<template>
  <!--
    Note we don't need .value inside templates because
    refs are automatically "unwrapped" in templates.
  -->
  <h1>{{ message }}</h1>
  
  <button @click="reverseMessage">Reverse Message</button>
  
  <button @click="message += '*'">Append "*"</button>
  
  <a href="https://vuejs.org" @click.prevent="notify">
    A link with e.preventDefault()
  </a>
</template>

<style>
button, a {
  display: block;
  margin-bottom: 1em;
}
</style>
