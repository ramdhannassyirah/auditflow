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
  <div class="grid grid-cols-3 min-h-screen">
    <!-- Form Section -->
    <div class="p-10 px-16 flex flex-col">
      <div class="logo mb-10">
        <a href="/" class="font-bold text-2xl">
          <span class="text-primary">audit</span>
          <span class="text-blue-600">flow</span>
        </a>
      </div>
      <h1 class="text-2xl font-semibold">Sign Up</h1>
      <div class="mt-4 text-center">
        <button
          @click="signUpWithGoogle"
          class="w-full p-2 border rounded-lg flex justify-center items-center"
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
        <span
          style="
            border-bottom: 1px solid rgb(219, 219, 219);
            height: 1px;
            flex: 1 1 0%;
          "
        ></span>
        <div
          class="or mb-2 px-4"
          style="color: rgb(153, 153, 153); font-size: 14px"
        >
          OR
        </div>
        <span
          style="
            border-bottom: 1px solid rgb(219, 219, 219);
            height: 1px;
            flex: 1 1 0%;
          "
        ></span>
      </div>
      <form @submit.prevent="handleSignup">
        <div class="mb-4">
          <label class="block text-gray-700">Email</label>
          <input
            type="email"
            v-model="email"
            class="w-full p-2 border rounded-lg"
            required
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700">Password</label>
          <input
            type="password"
            v-model="password"
            class="w-full p-2 border rounded-lg"
            required
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700">Confirm Password</label>
          <input
            type="password"
            v-model="confirmPassword"
            class="w-full p-2 border rounded-lg"
            required
          />
        </div>
        <button
          type="submit"
          class="w-full bg-blue-600 text-white p-2 rounded-lg hover:bg-blue-700"
        >
          Sign Up
        </button>
      </form>
      <p class="mt-4 text-gray-600">
        Already have an account?
        <a href="/" class="text-blue-600">Login</a>
      </p>
    </div>

    <!-- Image Section -->
    <div class="col-span-2 w-full flex">
      <img src="../assets/images/sign-up.svg" class="w-full" alt="Sign Up" />
    </div>
  </div>
</template>
