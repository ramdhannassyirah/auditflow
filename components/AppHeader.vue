<template>
  <header>
    <nav class="border-b-2 fixed w-full z-50 bg-white">
      <div
        class="max-w-7xl mx-auto flex justify-between items-center py-3 px-4 xl:px-0"
      >
        <!-- Logo -->
        <div class="logo">
          <a href="/" class="font-bold text-2xl">
            <span class="text-primary">audit</span>
            <span class="text-blue-600">flow</span>
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden lg:block flex-1 pl-4">
          <ul class="flex items-center gap-6 text-sm">
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white transition-colors"
                to="/feature"
              >
                Fitur
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white transition-colors"
                to="/price"
              >
                Harga
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white transition-colors"
                to="/article"
              >
                Artikel
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white transition-colors"
                to="/contact"
              >
                Kontak
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Desktop Auth Buttons -->
        <div class="hidden md:flex gap-4 text-sm items-center">
          <RouterLink
            to="/login"
            class="hover:text-blue-600 transition-colors font-medium"
          >
            Masuk
          </RouterLink>
          <RouterLink
            to="/signup"
            class="bg-primary px-4 py-2 rounded-md text-white font-semibold hover:bg-primary/90 transition-colors"
          >
            Mulai Sekarang
          </RouterLink>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="isMenuOpen = !isMenuOpen"
          class="lg:hidden ml-4 text-gray-600 focus:outline-none"
          aria-label="Toggle menu"
        >
          <svg
            v-if="!isMenuOpen"
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg
            v-else
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div
        v-if="isMenuOpen"
        class="lg:hidden absolute top-full left-0 right-0 bg-white shadow-md pb-4 px-4 border-b z-50"
      >
        <ul class="flex flex-col gap-4 py-4">
          <li>
            <NuxtLink
              @click="isMenuOpen = false"
              class="block p-2 hover:bg-blue-600 hover:text-white rounded-md transition-colors"
              to="/feature"
            >
              Fitur
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              @click="isMenuOpen = false"
              class="block p-2 hover:bg-blue-600 hover:text-white rounded-md transition-colors"
              to="/price"
            >
              Harga
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              @click="isMenuOpen = false"
              class="block p-2 hover:bg-blue-600 hover:text-white rounded-md transition-colors"
              to="/article"
            >
              Artikel
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              @click="isMenuOpen = false"
              class="block p-2 hover:bg-blue-600 hover:text-white rounded-md transition-colors"
              to="/contact"
            >
              Kontak
            </NuxtLink>
          </li>
          <li>
            <RouterLink
              to="/signup"
              class="bg-primary px-3 py-1.5 rounded-md text-white text-sm font-semibold"
            >
              Mulai Sekarang
            </RouterLink>
          </li>
          <li class="md:hidden">
            <NuxtLink
              @click="isMenuOpen = false"
              class="block p-2 hover:bg-blue-600 hover:text-white rounded-md transition-colors"
              to="/login"
            >
              Masuk
            </NuxtLink>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from "vue";

// State for mobile menu toggle
const isMenuOpen = ref(false);
</script>
