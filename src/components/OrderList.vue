<script setup>
import { ref } from "vue";

const items = ref([
  { name: "Cucumber", count: 0 },
  { name: "Carrot", count: 0 },
  { name: "Corn", count: 100 },
]);

function increment(index) {
  items.value[index].count++;
}

function decrement(index) {
  if (items.value[index].count > 0) {
    items.value[index].count--;
  }
}
</script>

<template>
  <div>
    <h1>Order Items</h1>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item.name }}
        <button @click="decrement(index)">-</button>
        {{ item.count }}
        <button @click="increment(index)">+</button>
      </li>
    </ul>
  </div>
</template>
