<script setup>
import { inject } from "vue";

const sharedState = inject("sharedState");
</script>

<template>
  <div>
    <h1>Second Child Component</h1>
    <p>Count: {{ sharedState.count }}</p>
    <button @click="sharedState.increment">Increment</button>
    <button @click="sharedState.decrement">Decrement</button>
  </div>
</template>
