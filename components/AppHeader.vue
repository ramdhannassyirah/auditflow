<template>
  <header>
    <nav class="border-b-2 fixed w-full z-50 bg-white">
      <div class="max-w-7xl mx-auto flex gap-6 items-center py-3 px-2 xl:px-0">
        <div class="logo">
          <a href="/" class="font-bold text-2xl"
            ><span class="text-primary">audit</span>
            <span class="text-blue-600">flow</span>
          </a>
        </div>
        <div class="flex-1 pl-4 hidden lg:block">
          <ul class="flex items-center gap-6 text-sm">
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white"
                to="/feature"
              >
                Fitur
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white"
                to="/price"
              >
                Harga
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white"
                to="/article"
              >
                Artikel
              </NuxtLink>
            </li>
            <li>
              <NuxtLink
                class="hover:bg-blue-600 p-2 rounded-md hover:text-white"
                to="/contact"
              >
                Kontak
              </NuxtLink>
            </li>
          </ul>
        </div>
        <div class="flex gap-4 text-sm">
          <RouterLink
            to="/signup"
            class="bg-primary px-4 py-2 rounded-md text-white font-semibold"
          >
            Mulai Sekarang
          </RouterLink>
          <button class="hidden md:block">Masuk</button>
        </div>
      </div>
    </nav>
  </header>
</template>
