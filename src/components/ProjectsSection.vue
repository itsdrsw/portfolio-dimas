<template>
  <!-- bg-gray-50 untuk membedakan dengan section Experience sebelumnya -->
  <section
    id="projects"
    class="py-24 bg-gray-50 dark:bg-gray-950 transition-colors duration-300"
  >
    <div class="max-w-6xl mx-auto px-6">
      <!-- Judul Section -->
      <div class="text-center mb-16 project-header opacity-0">
        <h2
          class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4"
        >
          Proyek Unggulan
        </h2>
        <div
          class="w-16 h-1 bg-blue-600 dark:bg-blue-500 mx-auto rounded-full mb-6"
        ></div>
        <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">
          Beberapa studi kasus nyata dan aplikasi yang telah saya kembangkan,
          mulai dari platform berbasis web hingga sistem cerdas berbasis AI dan
          IoT.
        </p>
      </div>

      <!-- Grid Proyek -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="project-card opacity-0 group bg-white dark:bg-gray-900 rounded-2xl overflow-hidden border border-gray-200 dark:border-gray-800 hover:border-blue-500 dark:hover:border-blue-500 shadow-sm hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2"
        >
          <!-- Gambar Proyek (Placeholder) -->
          <div
            class="h-48 bg-gray-200 dark:bg-gray-800 relative overflow-hidden"
          >
            <div
              class="absolute inset-0 flex items-center justify-center text-gray-400 dark:text-gray-600 font-medium"
            >
              [Screenshot {{ project.title }}]
            </div>
            <!-- Overlay saat hover -->
            <div
              class="absolute inset-0 bg-blue-600/90 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"
            >
              <a
                href="#"
                class="px-6 py-2 bg-white text-blue-600 font-semibold rounded-full transform translate-y-4 group-hover:translate-y-0 transition-all duration-300"
              >
                Detail Proyek
              </a>
            </div>
          </div>

          <!-- Konten Proyek -->
          <div class="p-6">
            <h3
              class="text-xl font-bold text-gray-900 dark:text-white mb-2 group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors"
            >
              {{ project.title }}
            </h3>
            <p
              class="text-gray-600 dark:text-gray-400 text-sm mb-4 line-clamp-3 leading-relaxed"
            >
              {{ project.desc }}
            </p>

            <!-- Tech Stack Tags -->
            <div class="flex flex-wrap gap-2 mt-auto">
              <span
                v-for="(tech, idx) in project.techs"
                :key="idx"
                class="px-2 py-1 bg-blue-50 dark:bg-blue-900/30 text-blue-600 dark:text-blue-400 text-xs font-medium rounded-md"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>

      <!-- Tombol Lihat Semua (Opsional) -->
      <div class="text-center mt-12 project-header opacity-0">
        <a
          href="https://github.com/"
          target="_blank"
          class="inline-flex items-center px-6 py-3 border border-gray-300 dark:border-gray-700 hover:border-blue-600 dark:hover:border-blue-500 text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-500 font-medium rounded-lg transition-all duration-300"
        >
          <svg
            class="w-5 h-5 mr-2"
            fill="currentColor"
            viewBox="0 0 24 24"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
              clip-rule="evenodd"
            ></path>
          </svg>
          Lihat Repositori GitHub
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

// Data Proyek Terpilih dari CV
const projects = ref([
  {
    title: "Situri",
    desc: "Sistem deteksi dini Tuberkulosis (TB paru) berbasis web yang dilengkapi dengan REST API dan Machine Learning menggunakan algoritma Naïve Bayes." /*[cite: 1] */,
    techs: [
      "Web",
      "Machine Learning",
      "REST API",
      "Naïve Bayes",
    ] /*[cite: 1] */,
  },
  {
    title: "Sistem Sortir Kentang",
    desc: "Sistem otomatisasi IoT untuk menyortir kentang berdasarkan ukuran, memanfaatkan Pengolahan Citra (Image Processing) dan Computer Vision." /*[cite: 1] */,
    techs: ["IoT", "Computer Vision", "Image Processing"] /*[cite: 1] */,
  },
  {
    title: "Kantinmu",
    desc: "Aplikasi pemesanan makanan kantin berbasis Web dengan fitur manajemen akses multi-peran dan pelaporan keuangan otomatis yang terintegrasi." /*[cite: 1] */,
    techs: ["Web App", "Multi-role", "Finance Report"] /*[cite: 1] */,
  },
  {
    title: "Cantara",
    desc: "Aplikasi pemesanan kue cross-platform (Web & Mobile) yang dilengkapi penjadwalan pesanan, pelacakan transaksi, dan dasbor manajemen penjual." /*[cite: 1] */,
    techs: ["Web", "Mobile", "Cross-platform"] /*[cite: 1] */,
  },
  {
    title: "Get Pharmacy",
    desc: "Aplikasi manajemen operasional apotek berbasis Desktop terpadu untuk pencatatan transaksi POS, pengelolaan resep, dan pelaporan keuangan." /*[cite: 1] */,
    techs: ["Desktop", "Java", "Point of Sale"] /*[cite: 1] */,
  },
  {
    title: "Edustupa",
    desc: "Aplikasi skrining mandiri dan rekam jejak deteksi Tuberkulosis (TB) Paru menggunakan algoritma klasifikasi Decision Tree (C4.5)." /*[cite: 1] */,
    techs: ["Machine Learning", "Decision Tree (C4.5)"] /*[cite: 1] */,
  },
]);

onMounted(() => {
  // Animasi Judul dan Tombol Bawah
  gsap.utils.toArray(".project-header").forEach((header) => {
    gsap.to(header, {
      scrollTrigger: {
        trigger: header,
        start: "top 85%",
      },
      y: 0,
      opacity: 1,
      duration: 0.8,
      ease: "power3.out",
    });
  });

  // Animasi Kartu Proyek (Berurutan)
  gsap.to(".project-card", {
    scrollTrigger: {
      trigger: "#projects",
      start: "top 75%",
    },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });
});
</script>

<style scoped>
/* State awal animasi untuk kartu */
.project-card,
.project-header {
  transform: translateY(30px);
}
</style>
