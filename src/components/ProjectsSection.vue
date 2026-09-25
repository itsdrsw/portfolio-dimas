<template>
  <section
    id="projects"
    class="relative py-32 bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 font-sans overflow-hidden"
  >
    <!-- Pattern Grid Halus -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow -->
    <div
      class="absolute top-1/3 right-0 lg:-right-48 w-[400px] h-[400px] md:w-[700px] md:h-[700px] bg-green-400 dark:bg-[#9DC183] opacity-[0.04] blur-[120px] md:blur-[150px] rounded-full pointer-events-none z-0 transition-colors duration-500"
    ></div>

    <div class="max-w-7xl mx-auto px-6 relative z-10">
      <!-- Header Section -->
      <div class="mb-20 text-left md:text-center flex flex-col md:items-center">
        <div class="flex items-center gap-4 mb-4 project-header-el opacity-0">
          <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
          <span
            class="uppercase tracking-[0.2em] text-xs font-bold text-gray-500 dark:text-gray-400"
          >
            Proyek Unggulan
          </span>
          <div
            class="hidden md:block w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"
          ></div>
        </div>
        <h2
          class="text-3xl md:text-5xl font-extrabold text-gray-900 dark:text-white mb-6 leading-[1.2] tracking-tight project-header-el opacity-0"
        >
          Karya yang telah saya bangun.
        </h2>
        <p
          class="text-gray-600 dark:text-gray-400 text-base md:text-lg max-w-2xl leading-relaxed font-light project-header-el opacity-0"
        >
          Studi kasus dan aplikasi yang merepresentasikan pengalaman saya dalam
          pengembangan web, aplikasi mobile, implementasi machine learning, dan
          solusi perangkat lunak praktis.
        </p>
      </div>

      <!-- Loading State -->
      <div
        v-if="isLoading"
        class="text-center py-20 text-green-600 dark:text-[#9DC183] animate-pulse"
      >
        Memuat data proyek dari Supabase...
      </div>

      <!-- Project Showcase Grid -->
      <div v-else class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12">
        <div
          v-for="(project, index) in projects"
          :key="project.id"
          :class="[
            'project-card opacity-0 group flex flex-col rounded-2xl border border-gray-200 dark:border-white/5 bg-white/60 dark:bg-white/[0.015] backdrop-blur-md overflow-hidden transition-all duration-500 hover:border-green-400 dark:hover:border-[#9DC183]/40 hover:-translate-y-2 hover:shadow-2xl hover:shadow-green-500/5',
            index === 0 ? 'md:col-span-2 md:flex-row' : '',
          ]"
        >
          <!-- Area Gambar (Visual Dominan) -->
          <div
            :class="[
              'relative overflow-hidden bg-gray-200 dark:bg-[#111613]',
              index === 0
                ? 'md:w-3/5 min-h-[300px] md:min-h-[400px]'
                : 'w-full h-60 md:h-64',
            ]"
          >
            <!-- Angka Proyek Besar di Latar -->
            <div
              class="absolute top-4 right-6 text-gray-400/30 dark:text-white/10 font-sans text-5xl md:text-7xl font-black group-hover:text-green-500/20 dark:group-hover:text-[#9DC183]/20 transition-colors duration-500 z-10 pointer-events-none"
            >
              {{ project.num }}
            </div>

            <!-- Gambar Asli dari Supabase -->
            <img
              v-if="project.image"
              :src="project.image"
              :alt="project.title"
              class="w-full h-full object-cover transform group-hover:scale-[1.03] transition-transform duration-700 ease-out relative z-0"
            />

            <!-- Fallback jika tidak ada gambar -->
            <div
              v-else
              class="w-full h-full transform group-hover:scale-[1.03] transition-transform duration-700 ease-out flex items-center justify-center border-r border-gray-200 dark:border-white/5 relative z-0"
            >
              <span class="text-gray-400 dark:text-gray-600 font-mono text-sm">
                [ No Image ]
              </span>
            </div>
          </div>

          <!-- Area Konten -->
          <div
            :class="[
              'flex flex-col p-8 md:p-10 relative z-20',
              index === 0 ? 'md:w-2/5 justify-center' : 'w-full flex-grow',
            ]"
          >
            <div class="mb-4">
              <span
                class="text-green-600 dark:text-[#9DC183] text-[10px] md:text-xs font-bold tracking-[0.2em] uppercase"
              >
                {{ project.category }}
              </span>
            </div>

            <h3
              class="text-2xl md:text-3xl font-extrabold text-gray-900 dark:text-white mb-4 group-hover:text-green-600 dark:group-hover:text-[#9DC183] transition-colors duration-300"
            >
              {{ project.title }}
            </h3>

            <p
              class="text-gray-600 dark:text-gray-400 text-sm md:text-base leading-relaxed mb-8"
            >
              {{ project.desc }}
            </p>

            <!-- Tech Pills -->
            <div class="flex flex-wrap gap-2 mb-10 mt-auto">
              <span
                v-for="(tech, idx) in project.techs"
                :key="idx"
                class="px-3 py-1 bg-gray-100 dark:bg-black/40 text-gray-600 dark:text-gray-400 text-[11px] font-medium rounded-full border border-gray-200 dark:border-white/10 shadow-sm"
              >
                {{ tech }}
              </span>
            </div>

            <!-- Action Link -->
            <a
              href="#"
              class="inline-flex items-center text-gray-900 dark:text-white font-semibold text-sm group/btn w-max"
            >
              Lihat Proyek
              <svg
                class="w-4 h-4 ml-2 transform group-hover/btn:translate-x-1 group-hover/btn:-translate-y-1 group-hover/btn:text-green-600 dark:group-hover/btn:text-[#9DC183] transition-all duration-300"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M17 8l4 4m0 0l-4 4m4-4H3"
                ></path>
              </svg>
            </a>
          </div>
        </div>
      </div>

      <!-- Secondary Action (View All) -->
      <div class="mt-20 text-center project-header-el opacity-0">
        <a
          href="https://github.com/dimasdharmasetiawan"
          target="_blank"
          class="inline-flex items-center px-6 py-3 border border-gray-300 dark:border-gray-700 text-gray-600 dark:text-gray-400 hover:text-green-600 dark:hover:text-[#9DC183] hover:border-green-600 dark:hover:border-[#9DC183] text-sm font-bold uppercase tracking-wider rounded-lg transition-all duration-300"
        >
          Lihat Semua Repositori
          <svg
            class="w-4 h-4 ml-2"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
            ></path>
          </svg>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, nextTick } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import { supabase } from "./supabase.js"; // Pastikan path ini sesuai dengan file konfigurasi Supabase Anda

gsap.registerPlugin(ScrollTrigger);

const isDark = ref(false);
const projects = ref([]);
const isLoading = ref(true);

// Fungsi untuk menarik data dari Supabase
async function fetchProjects() {
  const { data, error } = await supabase
    .from("proyek")
    .select("*")
    .order("id", { ascending: false });

  if (!error && data) {
    // Format data agar cocok dengan desain UI template Anda
    projects.value = data.map((item, index) => {
      // Deteksi jika proyek ini SITURI untuk mengubah kategori (Opsional)
      const isSituri = item.nama.toLowerCase().includes("situri");

      return {
        id: item.id,
        num: String(index + 1).padStart(2, "0"),
        category: isSituri ? "Web & Machine Learning" : "Selected Work",
        title: item.nama,
        desc: item.deskripsi,
        // Pecah string komponen menjadi array
        techs: item.komponen
          ? item.komponen.split(",").map((t) => t.trim())
          : [],
        image: item.gambar,
      };
    });

    // Sort khusus agar SITURI berada di urutan pertama (index 0 / gambar paling besar)
    const situriIndex = projects.value.findIndex((p) =>
      p.title.toLowerCase().includes("situri"),
    );
    if (situriIndex > 0) {
      const situriItem = projects.value.splice(situriIndex, 1)[0];
      projects.value.unshift(situriItem);
      // Urutkan ulang nomornya
      projects.value.forEach((p, idx) => {
        p.num = String(idx + 1).padStart(2, "0");
      });
    }
  }

  isLoading.value = false;

  // JALANKAN GSAP SETELAH DOM TER-UPDATE DENGAN DATA BARU
  nextTick(() => {
    initGSAP();
    ScrollTrigger.refresh();
  });
}

// Pisahkan fungsi animasi GSAP agar bisa dipanggil setelah loading selesai
function initGSAP() {
  gsap.to(".project-header-el", {
    scrollTrigger: { trigger: "#projects", start: "top 85%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  gsap.to(".project-card", {
    scrollTrigger: { trigger: "#projects", start: "top 75%" },
    y: 0,
    opacity: 1,
    duration: 1,
    stagger: 0.2,
    ease: "power3.out",
  });
}

onMounted(() => {
  // Dark mode observer
  isDark.value = document.documentElement.classList.contains("dark");
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  // Panggil fungsi tarik data saat komponen dimuat
  fetchProjects();
});
</script>

<style scoped>
.project-header-el {
  transform: translateY(30px);
}
.project-card {
  transform: translateY(50px);
}

.bg-grid-dark {
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.08) 1px, transparent 1px);
  background-size: 40px 40px;
}
.bg-grid-light {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
}
</style>
