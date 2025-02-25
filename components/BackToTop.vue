<template>
  <div
    class="fixed z-50 bottom-3 right-6 flex gap-2 items-end space-y-3 transition-opacity duration-500 ease-in-out"
    :class="{ 'opacity-100': showButton, 'opacity-0': !showButton }"
  >
    <!-- Tombol Back to Top -->
    <a
      href="#"
      @click.prevent="scrollToTop"
      class="bg-red-500 p-3 rounded-full shadow-lg cursor-pointer flex items-center justify-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        stroke="white"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="lucide lucide-arrow-up"
      >
        <path d="m5 12 7-7 7 7" />
        <path d="M12 19V5" />
      </svg>
    </a>

    <!-- Tombol WhatsApp -->
    <!-- <a
      :href="whatsappLink"
      target="_blank"
      class="shadow-lg p-2 rounded-full bg-green-600 cursor-pointer flex items-center justify-center"
    >
      <img src="../../assets/images/whatsapp2.png" class="" alt="" />
    </a> -->
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const showButton = ref(false);
const whatsappNumber = "6281234567890"; // Ganti dengan nomor WhatsApp
const whatsappLink = ref(`https://wa.me/${whatsappNumber}`);

const handleScroll = () => {
  showButton.value = window.scrollY > 200; // Muncul setelah scroll lebih dari 200px
};

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
