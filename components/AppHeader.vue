<template>
  <header>
    <nav class="border-b-2 fixed w-full z-50 bg-white">
      <div class="max-w-7xl mx-auto flex gap-6 items-center py-3">
        <div class="logo">
          <a href="/" class="font-bold text-2xl"
            ><span class="text-primary">audit</span>
            <span class="text-blue-600">flow</span>
          </a>
        </div>
        <div class="flex-1 pl-4">
          <ul class="flex items-center gap-4 text-sm">
            <li>
              <NuxtLink to="/"> Produk </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/"> Harga </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/"> Artikel </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/contact"> Kontak </NuxtLink>
            </li>
          </ul>
        </div>
        <div class="flex gap-4 text-sm">
          <button
            class="bg-primary px-4 py-2 rounded-md text-white font-semibold"
          >
            Mulai Sekarang
          </button>
          <button>Masuk</button>
        </div>
      </div>
    </nav>
  </header>
</template>
