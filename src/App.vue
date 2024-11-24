<script setup>
import ChildComponent from "./components/ChildComponent.vue";
import HelloWorld from "./components/HelloWorld.vue";
import { ref, reactive, provide } from "vue";

const sharedState = reactive({
  count: 0,
  increment() {
    this.count++;
  },
  decrement() {
    this.count--;
  },
});

provide("sharedState", sharedState);

const message = ref("Hello from Parent Component");

const updateMessage = () => {
  message.value = "Hello from Parent Component Updated";
};

provide("message", message);
provide("updateMessage", updateMessage);
</script>

<template>
  <div>
    <h1>Parent Component</h1>
    <button @click="updateMessage">Update Message</button>
    <ChildComponent />
    <HelloWorld />
    <p>Count: {{ sharedState.count }}</p>
    <button @click="sharedState.increment">Increment</button>
    <button @click="sharedState.decrement">Decrement</button>
  </div>
</template>
