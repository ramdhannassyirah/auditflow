<template>
  <section class="max-w-7xl mx-auto px-4 py-12 md:py-16">
    <!-- Header Section -->
    <div
      class="flex flex-col max-w-2xl mx-auto justify-center text-center items-center gap-4 mb-12"
    >
      <p
        class="text-blue-600 bg-secondary/20 px-4 py-1 font-semibold rounded-full"
      >
        Fitur
      </p>
      <h1
        class="antialiased text-foreground text-3xl font-black leading-relaxed tracking-normal md:text-4xl lg:text-5xl"
      >
        Kembangkan bisnis Anda dengan Auditflow
      </h1>
      <p class="text-gray-600 max-w-xl">
        Rencanakan, eksekusi, dan pantau operasi teknisi lapangan harian Anda
        dalam satu platform.
      </p>
    </div>

    <!-- Features Content Section -->
    <div class="pt-6">
      <div class="flex flex-col lg:flex-row gap-8">
        <!-- Sidebar Buttons - Horizontal on mobile, Vertical on desktop -->
        <div class="w-full lg:w-auto">
          <h1 class="text-xl md:text-2xl font-semibold mb-4">
            Fitur - Fitur :
          </h1>

          <!-- Mobile Tabs (Horizontal Scrolling) -->
          <div class="flex lg:hidden overflow-x-auto pb-4 gap-3 snap-x">
            <button
              v-for="(item, index) in menuItems"
              :key="index"
              @click="selectedContent = item.id"
              :class="[
                'bg-white border border-gray-200 py-2 px-4 rounded-md whitespace-nowrap transition-colors snap-start',
                selectedContent === item.id
                  ? 'bg-primary text-danger'
                  : 'hover:bg-gray-100',
              ]"
            >
              {{ item.title }}
            </button>
          </div>

          <!-- Desktop Vertical Buttons -->
          <div class="hidden lg:flex flex-col gap-3">
            <button
              v-for="(item, index) in menuItems"
              :key="index"
              @click="selectedContent = item.id"
              :class="[
                'py-2 px-6 w-56 rounded-md text-left transition-colors',
                selectedContent === item.id
                  ? 'bg-primary text-white'
                  : 'bg-white border border-gray-200 hover:bg-gray-100',
              ]"
            >
              {{ item.title }}
            </button>
          </div>
        </div>

        <!-- Dynamic Content -->
        <div
          class="flex-1 p-4 bg-white rounded-lg border border-gray-200 shadow-sm"
        >
          <div v-if="selectedContent === 'visi'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Menjadi perusahaan terkemuka yang memberikan dampak positif bagi
              masyarakat dan lingkungan.
            </p>
          </div>

          <div v-else-if="selectedContent === 'misi'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Lorem, ipsum.</h2>
            <ul class="list-disc pl-6 space-y-2">
              <li>Mengembangkan produk dan layanan berkualitas</li>
              <li>Memberikan pelayanan terbaik kepada pelanggan</li>
              <li>Membangun tim yang profesional dan berdedikasi</li>
            </ul>
          </div>

          <div v-else-if="selectedContent === 'sejarah'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Didirikan pada tahun 2010, perusahaan kami telah berkembang
              menjadi salah satu pemimpin di industri ini.
            </p>
          </div>

          <div v-else-if="selectedContent === 'leadership'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Lorem, ipsum.</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div class="p-4 border rounded">
                <h3 class="font-bold">CEO</h3>
                <p>John Doe</p>
              </div>
              <div class="p-4 border rounded">
                <h3 class="font-bold">CTO</h3>
                <p>Jane Smith</p>
              </div>
            </div>
          </div>

          <div v-else-if="selectedContent === 'ethical'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Kami berkomitmen untuk menjalankan bisnis dengan integritas dan
              etika yang tinggi.
            </p>
          </div>

          <div v-else-if="selectedContent === 'hubungan'" class="space-y-4">
            <h2 class="text-xl md:text-2xl font-bold">Hubungan Kelembagaan</h2>
            <p>
              Kami menjalin kerjasama dengan berbagai institusi dan lembaga
              untuk mencapai tujuan bersama.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const selectedContent = ref("visi");
const menuItems = ref([
  { id: "visi", title: "Fitur A" },
  { id: "misi", title: "Fitur B" },
  { id: "sejarah", title: "Fitur C" },
  { id: "leadership", title: "Fitur D" },
  { id: "ethical", title: "Fitur E" },
  { id: "hubungan", title: "Fitur F" },
]);
</script>
