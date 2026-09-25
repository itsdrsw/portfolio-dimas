<template>
  <section
    id="experience"
    class="py-24 bg-white dark:bg-gray-900 transition-colors duration-300"
  >
    <div class="max-w-4xl mx-auto px-6">
      <!-- Judul Section -->
      <div class="text-center mb-16 exp-header opacity-0">
        <h2
          class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4"
        >
          Pengalaman Kerja
        </h2>
        <div
          class="w-16 h-1 bg-blue-600 dark:bg-blue-500 mx-auto rounded-full"
        ></div>
      </div>

      <!-- Wadah Timeline -->
      <div
        class="relative border-l-2 border-gray-200 dark:border-gray-700 ml-3 md:ml-6 timeline-line"
      >
        <!-- Looping Pengalaman (Bisa ditambah jika ada pengalaman lain ke depannya) -->
        <div
          v-for="(exp, index) in experiences"
          :key="index"
          class="mb-12 relative pl-8 md:pl-12 exp-item opacity-0"
        >
          <!-- Titik/Node Timeline -->
          <div
            class="absolute -left-[9px] top-1.5 w-4 h-4 bg-blue-600 dark:bg-blue-500 rounded-full border-4 border-white dark:border-gray-900 shadow-sm"
          ></div>

          <!-- Konten Pengalaman -->
          <div
            class="bg-gray-50 dark:bg-gray-800 p-6 md:p-8 rounded-2xl border border-gray-100 dark:border-gray-700 shadow-sm hover:shadow-md transition-shadow"
          >
            <div
              class="flex flex-col md:flex-row md:justify-between md:items-center mb-4"
            >
              <div>
                <h3
                  class="text-xl md:text-2xl font-bold text-gray-900 dark:text-white"
                >
                  {{ exp.role }}
                </h3>
                <p class="text-blue-600 dark:text-blue-400 font-semibold mt-1">
                  {{ exp.company }}
                </p>
              </div>
              <span
                class="inline-block mt-2 md:mt-0 px-3 py-1 bg-gray-200 dark:bg-gray-700 text-gray-700 dark:text-gray-300 text-sm font-medium rounded-full"
              >
                {{ exp.period }}
              </span>
            </div>

            <ul class="space-y-2 mt-4">
              <li
                v-for="(task, idx) in exp.tasks"
                :key="idx"
                class="flex items-start text-gray-600 dark:text-gray-400 text-base leading-relaxed"
              >
                <span class="mr-3 text-blue-500 mt-1">•</span>
                <span>{{ task }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

// Data Pengalaman diambil dari CV
const experiences = ref([
  {
    role: "Tim Technical - Intern",
    company: "PT. Adaptiv Solusi Informatika",
    period: "Agustus 2025 - Desember 2025",
    tasks: [
      "Mempelajari dan menganalisis proses bisnis inti menggunakan sistem ERP Odoo, meliputi manajemen Master Data, siklus Procure-to-Pay (P2P), dan Sell-to-Cash." /*[cite: 1] */,
      "Menyusun dan mengembangkan dokumentasi teknis (user manual/guide) komprehensif untuk penggunaan modul dan template Odoo." /*[cite: 1] */,
      "Melakukan kustomisasi Odoo XML View menggunakan inheritance dan XPath, termasuk modifikasi form view, tree view, badge status, field, serta filter." /*[cite: 1] */,
      "Melakukan pengelolaan master data Odoo, termasuk proses import/export data produk dan BOM menggunakan spreadsheet." /*[cite: 1] */,
      "Melakukan validasi hak akses pengguna berdasarkan role pada sistem Odoo." /*[cite: 1] */,
    ],
  },
]);

onMounted(() => {
  // Animasi Judul
  gsap.to(".exp-header", {
    scrollTrigger: {
      trigger: "#experience",
      start: "top 80%",
    },
    y: 0,
    opacity: 1,
    duration: 0.8,
    ease: "power3.out",
  });

  // Animasi Garis Timeline agar seolah-olah "menggambar" ke bawah
  gsap.from(".timeline-line", {
    scrollTrigger: {
      trigger: "#experience",
      start: "top 75%",
    },
    scaleY: 0,
    transformOrigin: "top left",
    duration: 1.5,
    ease: "power2.out",
  });

  // Animasi Kartu Pengalaman masuk dari samping
  gsap.to(".exp-item", {
    scrollTrigger: {
      trigger: ".timeline-line",
      start: "top 60%",
    },
    x: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.3,
    ease: "power3.out",
  });
});
</script>

<style scoped>
/* State awal untuk animasi GSAP agar tidak terlihat sebelum di-scroll */
.exp-item {
  transform: translateX(30px);
}
</style>
