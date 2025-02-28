<script setup>
definePageMeta({
  layout: false,
});

import { ref } from "vue";

const name = ref("");
const email = ref("");
const password = ref("");
const confirmPassword = ref("");

const handleSignup = () => {
  if (password.value !== confirmPassword.value) {
    alert("Passwords do not match!");
    return;
  }
  console.log("Signup:", {
    name: name.value,
    email: email.value,
    password: password.value,
  });
  // Tambahkan logika signup seperti API request di sini
};

const signUpWithGoogle = () => {
  console.log("Signing up with Google...");
  // Tambahkan logika autentikasi Google di sini
};
</script>

<template>
  <div
    class="min-h-screen flex flex-col-reverse md:grid md:grid-cols-2 lg:grid-cols-3"
  >
    <!-- Form Section - Full width on mobile, 1/3 on desktop -->
    <div class="p-6 md:p-8 lg:p-10 flex flex-col bg-white md:col-span-1">
      <div class="logo mb-8">
        <a href="/" class="font-bold text-2xl">
          <span class="text-primary">audit</span>
          <span class="text-blue-600">flow</span>
        </a>
      </div>

      <h1 class="text-2xl font-semibold">Sign Up</h1>

      <div class="mt-4">
        <button
          @click="signUpWithGoogle"
          class="w-full p-2 border rounded-lg flex justify-center items-center hover:bg-gray-50 transition-colors"
        >
          <img
            src="../assets/images/google.png"
            class="w-5 h-5 mr-2"
            alt="Google Icon"
          />
          Sign Up with Google
        </button>
      </div>

      <div class="w-full flex items-center my-6">
        <span class="border-b border-gray-200 h-0 flex-1"></span>
        <div class="mx-4 text-sm text-gray-400">OR</div>
        <span class="border-b border-gray-200 h-0 flex-1"></span>
      </div>

      <form @submit.prevent="handleSignup" class="w-full">
        <div class="mb-4">
          <label class="block text-gray-700 mb-1">Email</label>
          <input
            type="email"
            v-model="email"
            class="w-full p-2 border rounded-lg focus:ring-2 focus:ring-blue-300 focus:border-blue-500 outline-none"
            required
          />
        </div>

        <div class="mb-4">
          <label class="block text-gray-700 mb-1">Password</label>
          <input
            type="password"
            v-model="password"
            class="w-full p-2 border rounded-lg focus:ring-2 focus:ring-blue-300 focus:border-blue-500 outline-none"
            required
          />
        </div>

        <div class="mb-6">
          <label class="block text-gray-700 mb-1">Confirm Password</label>
          <input
            type="password"
            v-model="confirmPassword"
            class="w-full p-2 border rounded-lg focus:ring-2 focus:ring-blue-300 focus:border-blue-500 outline-none"
            required
          />
        </div>

        <button
          type="submit"
          class="w-full bg-blue-600 text-white p-2 rounded-lg hover:bg-blue-700 transition-colors"
        >
          Sign Up
        </button>
      </form>

      <p class="mt-6 text-gray-600 text-center">
        Already have an account?
        <a href="/" class="text-blue-600 hover:underline">Login</a>
      </p>
    </div>

    <!-- Image Section - Hidden on small mobile, visible on medium+ screens -->
    <div
      class="md:col-span-1 lg:col-span-2 bg-blue-50 flex items-center justify-center p-6"
    >
      <img
        src="../assets/images/sign-up.svg"
        class="w-full max-w-md md:max-w-full h-auto object-contain"
        alt="Sign Up"
      />
    </div>
  </div>
</template>
