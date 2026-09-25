<template>
  <section
    id="experience"
    class="relative py-24 bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 font-sans overflow-hidden"
  >
    <!-- Pattern Grid Halus (Dinamis Light/Dark) -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow di KIRI untuk meneruskan alur zig-zag -->
    <div
      class="absolute top-1/2 -left-32 md:-left-48 -translate-y-1/2 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-green-400 dark:bg-[#9DC183] opacity-[0.05] blur-[100px] md:blur-[120px] rounded-full pointer-events-none z-0 transition-colors duration-500"
    ></div>

    <div class="max-w-4xl mx-auto px-6 relative z-10">
      <!-- Judul Section -->
      <div class="mb-16 md:mb-20 text-center flex flex-col items-center">
        <div class="flex items-center gap-4 mb-4 exp-header-el opacity-0">
          <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
          <span
            class="uppercase tracking-[0.2em] text-xs font-bold text-gray-500 dark:text-gray-400"
            >Experience</span
          >
          <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
        </div>
        <h2
          class="text-3xl md:text-4xl lg:text-5xl font-extrabold text-gray-900 dark:text-white mb-6 leading-[1.2] tracking-tight exp-header-el opacity-0"
        >
          Jejak Karir
        </h2>
      </div>

      <!-- Wadah Timeline -->
      <div
        class="relative border-l-2 border-gray-200 dark:border-white/10 ml-4 md:ml-8 timeline-line"
      >
        <!-- Looping Pengalaman -->
        <div
          v-for="(exp, index) in experiences"
          :key="index"
          class="mb-12 relative pl-8 md:pl-12 exp-item opacity-0 group"
        >
          <!-- Titik/Node Timeline (Menyala saat hover kartu) -->
          <div
            class="absolute -left-[9px] top-1.5 w-4 h-4 bg-gray-200 dark:bg-gray-800 rounded-full border-4 border-gray-50 dark:border-[#080B09] shadow-sm group-hover:bg-green-500 dark:group-hover:bg-[#9DC183] transition-colors duration-300"
          ></div>

          <!-- Kartu Pengalaman (Glassmorphism) -->
          <div
            class="p-6 md:p-8 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-md hover:bg-white/60 dark:hover:bg-white/[0.04] hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-500 hover:-translate-y-2 hover:shadow-xl hover:shadow-green-500/5"
          >
            <div
              class="flex flex-col md:flex-row md:justify-between md:items-start mb-6 gap-4"
            >
              <div>
                <h3
                  class="text-xl md:text-2xl font-bold text-gray-900 dark:text-white group-hover:text-green-600 dark:group-hover:text-[#9DC183] transition-colors"
                >
                  {{ exp.role }}
                </h3>
                <p
                  class="text-gray-600 dark:text-gray-400 font-medium mt-1 flex items-center gap-2"
                >
                  <svg
                    class="w-4 h-4 text-gray-400"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m3-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"
                    ></path>
                  </svg>
                  {{ exp.company }}
                </p>
              </div>

              <!-- Label Waktu -->
              <span
                class="inline-flex items-center px-3 py-1.5 bg-gray-100 dark:bg-white/5 border border-gray-200 dark:border-white/10 text-gray-600 dark:text-gray-400 text-xs font-semibold rounded-lg tracking-wide whitespace-nowrap"
              >
                {{ exp.period }}
              </span>
            </div>

            <!-- Daftar Tugas dengan Ikon Centang -->
            <ul class="space-y-3">
              <li
                v-for="(task, idx) in exp.tasks"
                :key="idx"
                class="flex items-start text-gray-600 dark:text-gray-400 text-[14px] md:text-[15px] leading-relaxed"
              >
                <div
                  class="mr-3 mt-1 text-green-500 dark:text-[#9DC183] flex-shrink-0"
                >
                  <svg
                    class="w-4 h-4"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M5 13l4 4L19 7"
                    ></path>
                  </svg>
                </div>
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

// Deteksi Light/Dark mode
const isDark = ref(false);

const experiences = ref([
  {
    role: "Tim Technical - Intern",
    company: "PT. Adaptiv Solusi Informatika",
    period: "Agustus 2025 - Desember 2025",
    tasks: [
      "Mempelajari dan menganalisis proses bisnis inti menggunakan sistem ERP Odoo, meliputi manajemen Master Data, siklus Procure-to-Pay (P2P), dan Sell-to-Cash.",
      "Menyusun dan mengembangkan dokumentasi teknis (user manual/guide) komprehensif untuk penggunaan modul dan template Odoo.",
      "Melakukan kustomisasi Odoo XML View menggunakan inheritance dan XPath, termasuk modifikasi form view, tree view, badge status, field, serta filter.",
      "Melakukan pengelolaan master data Odoo, termasuk proses import/export data produk dan BOM menggunakan spreadsheet.",
      "Melakukan validasi hak akses pengguna berdasarkan role pada sistem Odoo.",
    ],
  },
]);

onMounted(() => {
  // Observer untuk Light/Dark mode pattern
  isDark.value = document.documentElement.classList.contains("dark");
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  // Animasi Header
  gsap.to(".exp-header-el", {
    scrollTrigger: { trigger: "#experience", start: "top 80%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  // Animasi Garis Timeline dari atas ke bawah
  gsap.from(".timeline-line", {
    scrollTrigger: { trigger: "#experience", start: "top 75%" },
    scaleY: 0,
    transformOrigin: "top left",
    duration: 1.5,
    ease: "power2.out",
  });

  // Animasi Kartu masuk dari samping secara berurutan
  gsap.to(".exp-item", {
    scrollTrigger: { trigger: ".timeline-line", start: "top 65%" },
    x: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.3,
    ease: "power3.out",
  });
});
</script>

<style scoped>
.exp-header-el {
  transform: translateY(30px);
}
.exp-item {
  transform: translateX(30px);
}

/* Pola Grid dengan Opacity 0.08 */
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
