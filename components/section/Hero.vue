<template>
  <div class="relative mx-auto h-[500px] max-w-7xl overflow-hidden">
    <div
      v-for="(slide, index) in slides"
      :key="index"
      class="absolute inset-0 transition-opacity duration-1000 ease-in-out"
      :class="{
        'opacity-100': index === activeIndex,
        'opacity-0': index !== activeIndex,
      }"
      :style="{ backgroundImage: `url(${slide.image})` }"
    >
      <div class="absolute inset-0 bg-black opacity-50"></div>
      <h2 class="absolute bottom-10 left-10 text-white text-4xl font-bold">
        {{ slide.title }}
      </h2>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import eventImage from "@/assets/images/events-1.png";

const slides = [
  {
    title: "Welcome to Our Website",
    image: eventImage,
  },
  { title: "Experience the Best Services", image: "/images/hero2.jpg" },
  { title: "Join Us Today", image: eventImage },
];

const activeIndex = ref(0);

onMounted(() => {
  setInterval(() => {
    activeIndex.value = (activeIndex.value + 1) % slides.length;
  }, 5000);
});
</script>

<style>
/* Tambahkan styling jika perlu */
</style>
