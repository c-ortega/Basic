<script setup>
import { ref } from "vue";

const galleryItems = ref([
  { image: "/BridgeOne.jpg" },
  { image: "/BridgeTwo.jpg" },
  { image: "/BridgeThree.jpg" },
  { image: "/BridgeFour.jpg" },
  { image: "/BridgeFive.jpg" },
]);

const currentIndex = ref(0);

function nextImage() {
  currentIndex.value = (currentIndex.value + 1) % galleryItems.value.length;
}

function prevImage() {
  currentIndex.value =
    (currentIndex.value - 1 + galleryItems.value.length) %
    galleryItems.value.length;
}
</script>

<template>
  <div class="gallery-container">
    <button @click="prevImage">&#10094;</button>
    <img :src="galleryItems[currentIndex].image" class="gallery-image" />
    <button @click="nextImage">&#10095;</button>
  </div>
</template>

<style scoped>
.gallery-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.gallery-image {
  max-width: 600px;
  height: auto;
  border: 2px solid #ccc;
  border-radius: 10px;
}
button {
  background-color: #333;
  color: white;
  border: none;
  padding: 10px;
  font-size: 20px;
  cursor: pointer;
  border-radius: 5px;
}
button:hover {
  background-color: #555;
}
</style>
