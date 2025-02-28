<template>
  <section class="max-w-7xl mx-auto">
    <div
      class="flex flex-col max-w-2xl mx-auto justify-center text-center items-center gap-4"
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
      <p>
        Rencanakan, eksekusi, dan pantau operasi teknisi lapangan harian Anda
        dalam satu platform.
      </p>
    </div>
    <div class="pt-10">
      <div class="flex gap-4">
        <!-- Sidebar Buttons -->
        <div class="flex flex-col gap-4">
          <h1 class="text-2xl font-semibold">Fitur - Fitur :</h1>
          <button
            v-for="(item, index) in menuItems"
            :key="index"
            @click="selectedContent = item.id"
            class="bg-primary py-2 px-6 w-56 text-white rounded-md hover:bg-primary/80 transition-colors"
          >
            {{ item.title }}
          </button>
        </div>

        <!-- Dynamic Content -->
        <div class="flex-1 p-4">
          <div v-if="selectedContent === 'visi'" class="space-y-4">
            <h2 class="text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Menjadi perusahaan terkemuka yang memberikan dampak positif bagi
              masyarakat dan lingkungan.
            </p>
          </div>

          <div v-else-if="selectedContent === 'misi'" class="space-y-4">
            <h2 class="text-2xl font-bold">Lorem, ipsum.</h2>
            <ul class="list-disc pl-6 space-y-2">
              <li>Mengembangkan produk dan layanan berkualitas</li>
              <li>Memberikan pelayanan terbaik kepada pelanggan</li>
              <li>Membangun tim yang profesional dan berdedikasi</li>
            </ul>
          </div>

          <div v-else-if="selectedContent === 'sejarah'" class="space-y-4">
            <h2 class="text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Didirikan pada tahun 2010, perusahaan kami telah berkembang
              menjadi salah satu pemimpin di industri ini.
            </p>
          </div>

          <div v-else-if="selectedContent === 'leadership'" class="space-y-4">
            <h2 class="text-2xl font-bold">Lorem, ipsum.</h2>
            <div class="grid grid-cols-2 gap-4">
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
            <h2 class="text-2xl font-bold">Lorem, ipsum.</h2>
            <p>
              Kami berkomitmen untuk menjalankan bisnis dengan integritas dan
              etika yang tinggi.
            </p>
          </div>

          <div v-else-if="selectedContent === 'hubungan'" class="space-y-4">
            <h2 class="text-2xl font-bold">Hubungan Kelembagaan</h2>
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
  { id: "misi", title: "Fitur" },
  { id: "sejarah", title: "Fitur" },
  { id: "leadership", title: "Fitur" },
  { id: "ethical", title: "Fitur " },
  { id: "hubungan", title: "Fitur " },
]);
</script>
