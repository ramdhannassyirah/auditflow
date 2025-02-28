<template>
  <section
    class="max-w-7xl mx-auto my-10 p-10 rounded-md overflow-hidden px-2 xl:px-0"
  >
    <h1 class="lg:text-4xl text-xl font-bold text-center mb-6">
      Telah Dipercaya Oleh
    </h1>
    <div class="relative flex items-center overflow-hidden w-full">
      <!-- Wrapper untuk animasi -->
      <div class="flex animate-slide pt-6">
        <div
          v-for="(client, index) in clients"
          :key="index"
          class="flex-shrink-0 w-40 mx-4 text-center"
        >
          <img
            :src="client.logo"
            :alt="client.name"
            class="w-18 h-18 object-contain mx-auto"
          />
          <p class="mt-2 text-md font-semibold">{{ client.name }}</p>
        </div>
        <!-- Duplikasi untuk efek looping -->
        <div
          v-for="(client, index) in clients"
          :key="'dup-' + index"
          class="flex-shrink-0 w-40 mx-4 text-center"
        >
          <img
            :src="client.logo"
            :alt="client.name"
            class="w-18 h-18 object-contain mx-auto"
          />
          <p class="mt-2 text-md font-semibold">{{ client.name }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import googleImg from "@/assets/images/google.png";
const clients = [
  { name: "Google", logo: googleImg },
  { name: "Microsoft", logo: "/images/clients/microsoft.png" },
  { name: "Facebook", logo: "/images/clients/facebook.png" },
  { name: "Amazon", logo: "/images/clients/amazon.png" },
  { name: "Tesla", logo: "/images/clients/tesla.png" },
];
</script>

<style scoped>
@keyframes slide {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.animate-slide {
  display: flex;
  white-space: nowrap;
  animation: slide 10s linear infinite;
}
</style>
