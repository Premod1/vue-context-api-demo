<script setup>
import { inject } from "vue";

const message = inject("message");
const updateMessage = inject("updateMessage");
const sharedState = inject("sharedState");
</script>

<template>
  <div>
    <h2>Child Component</h2>
    <p>Message: {{ message }}</p>
    <button @click="updateMessage">Update Message</button>
    <p>Count: {{ sharedState.count }}</p>
    <button @click="sharedState.increment">Increment</button>
    <button @click="sharedState.decrement">Decrement</button>
  </div>
</template>
