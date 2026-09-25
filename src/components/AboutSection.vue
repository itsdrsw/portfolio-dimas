<template>
  <!-- Background disamakan persis dengan Hero -->
  <section
    id="about"
    class="py-24 bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 relative overflow-hidden font-sans"
  >
    <!-- Pattern Grid Halus yang berlanjut dari Hero -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow dipindah ke KIRI untuk transisi zig-zag yang natural dari Hero -->
    <div
      class="absolute top-1/4 -left-32 md:-left-48 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-green-400 dark:bg-[#9DC183] opacity-[0.05] blur-[100px] md:blur-[120px] rounded-full pointer-events-none transition-colors duration-500 z-0"
    ></div>

    <div class="max-w-7xl mx-auto px-6 relative z-10">
      <div
        class="grid grid-cols-1 lg:grid-cols-12 gap-16 lg:gap-12 items-center"
      >
        <!-- Kolom Kiri: Tipografi Editorial (6 Kolom) -->
        <div class="lg:col-span-6 flex flex-col justify-center">
          <div class="flex items-center gap-4 mb-8 about-el opacity-0">
            <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
            <span
              class="uppercase tracking-[0.2em] text-xs font-bold text-gray-500 dark:text-gray-400"
              >About Me</span
            >
          </div>

          <!-- Heading baru yang lebih kuat dan teknis -->
          <h2
            class="text-3xl md:text-4xl lg:text-5xl font-extrabold text-gray-900 dark:text-white mb-6 leading-[1.2] tracking-tight about-el opacity-0"
          >
            Merancang sistem terintegrasi dan solusi cerdas untuk dampak nyata.
          </h2>

          <!-- Deskripsi sesuai CV -->
          <div class="space-y-5">
            <p
              class="text-gray-600 dark:text-gray-400 text-base md:text-lg leading-relaxed font-light about-el opacity-0"
            >
              Lulusan D4 Teknik Informatika dengan pengalaman praktik langsung
              dalam pengembangan sistem dan analisis data dari desain awal
              hingga sistem berjalan. Selama studi, saya aktif mengambil studi
              kasus nyata, mulai dari digitalisasi UMKM hingga mengelola data
              rekam medis rumah sakit.
            </p>
            <p
              class="text-gray-600 dark:text-gray-400 text-base md:text-lg leading-relaxed font-light about-el opacity-0"
            >
              Berbekal pemahaman di bidang Software Quality Assurance (SQA),
              pengembangan mobile, dan Machine Learning, saya selalu berfokus
              untuk menerapkan keahlian teknis yang saya miliki guna memberikan
              dampak dan solusi nyata di industri teknologi.
            </p>
          </div>
        </div>

        <!-- Kolom Kanan: Panel Visual Editor Kode (6 Kolom) -->
        <div
          class="lg:col-span-6 about-code-container opacity-0 transform translate-x-8 relative z-10"
        >
          <!-- Window Code Editor -->
          <div
            class="rounded-2xl border border-gray-200 dark:border-white/10 bg-white/60 dark:bg-[#111613]/80 backdrop-blur-xl shadow-2xl overflow-hidden relative"
          >
            <div
              class="flex items-center px-5 py-3 border-b border-gray-200 dark:border-white/5 bg-gray-100/50 dark:bg-white/[0.02]"
            >
              <div class="flex space-x-2">
                <div
                  class="w-3 h-3 rounded-full bg-gray-300 dark:bg-gray-600 border border-gray-400 dark:border-gray-500/50"
                ></div>
                <div
                  class="w-3 h-3 rounded-full bg-gray-300 dark:bg-gray-600 border border-gray-400 dark:border-gray-500/50"
                ></div>
                <div
                  class="w-3 h-3 rounded-full bg-gray-300 dark:bg-gray-600 border border-gray-400 dark:border-gray-500/50"
                ></div>
              </div>
              <div
                class="mx-auto text-xs text-gray-500 dark:text-gray-500 font-mono tracking-wider"
              >
                developer.ts
              </div>
              <div class="w-11"></div>
            </div>

            <div
              class="p-6 md:p-8 overflow-x-auto text-[13px] md:text-[15px] font-mono leading-[2]"
            >
              <pre
                class="text-gray-800 dark:text-gray-300"
              ><span class="text-purple-600 dark:text-purple-400 font-semibold">const</span> <span class="text-blue-600 dark:text-blue-400 font-semibold">developer</span> <span class="text-gray-500 dark:text-gray-400">=</span> {
  <span class="text-gray-500 dark:text-gray-500">name:</span> <span class="text-green-600 dark:text-[#9DC183]">"Dimas Dharma Setiawan"</span>,
  <span class="text-gray-500 dark:text-gray-500">role:</span> <span class="text-green-600 dark:text-[#9DC183]">"Software Developer"</span>,
  <span class="text-gray-500 dark:text-gray-500">focus:</span> [
    <span class="text-green-600 dark:text-[#9DC183]">"Web Development"</span>,
    <span class="text-green-600 dark:text-[#9DC183]">"Mobile Development"</span>,
    <span class="text-green-600 dark:text-[#9DC183]">"Machine Learning"</span>
  ],
  <span class="text-gray-500 dark:text-gray-500">mindset:</span> <span class="text-green-600 dark:text-[#9DC183]">"Build. Learn. Improve."</span>
};</pre>
            </div>
          </div>
        </div>
      </div>

      <!-- Baris Bawah: Kartu Statistik Personal -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-16 lg:mt-24">
        <!-- Statistik 1: Tahun Pengalaman -->
        <div
          class="about-card opacity-0 relative group p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-md overflow-hidden hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-500 hover:-translate-y-2 hover:shadow-xl hover:shadow-green-500/5"
        >
          <!-- Garis Aksen Atas (Muncul saat Hover) -->
          <div
            class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-green-500 dark:via-[#9DC183] to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
          ></div>

          <div class="flex justify-between items-start mb-4">
            <h3
              class="text-4xl md:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-br from-gray-800 to-gray-500 dark:from-white dark:to-gray-500 group-hover:from-green-600 group-hover:to-green-400 dark:group-hover:from-[#9DC183] dark:group-hover:to-emerald-200 transition-all duration-500"
            >
              03<span class="text-2xl text-green-500 dark:text-[#9DC183]"
                >+</span
              >
            </h3>
            <div
              class="p-2.5 rounded-xl bg-gray-100 dark:bg-white/5 text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-500"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1.5"
                  d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
                ></path>
              </svg>
            </div>
          </div>
          <p
            class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mt-2"
          >
            Tahun Pengalaman
          </p>
        </div>

        <!-- Statistik 2: Proyek Selesai -->
        <div
          class="about-card opacity-0 relative group p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-md overflow-hidden hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-500 hover:-translate-y-2 hover:shadow-xl hover:shadow-green-500/5"
        >
          <div
            class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-green-500 dark:via-[#9DC183] to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
          ></div>

          <div class="flex justify-between items-start mb-4">
            <h3
              class="text-4xl md:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-br from-gray-800 to-gray-500 dark:from-white dark:to-gray-500 group-hover:from-green-600 group-hover:to-green-400 dark:group-hover:from-[#9DC183] dark:group-hover:to-emerald-200 transition-all duration-500"
            >
              11<span class="text-2xl text-green-500 dark:text-[#9DC183]"
                >+</span
              >
            </h3>
            <div
              class="p-2.5 rounded-xl bg-gray-100 dark:bg-white/5 text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-500"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1.5"
                  d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
                ></path>
              </svg>
            </div>
          </div>
          <p
            class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mt-2"
          >
            Proyek Selesai
          </p>
        </div>

        <!-- Statistik 3: Klien & Mitra Puas -->
        <div
          class="about-card opacity-0 relative group p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-md overflow-hidden hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-500 hover:-translate-y-2 hover:shadow-xl hover:shadow-green-500/5"
        >
          <div
            class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-green-500 dark:via-[#9DC183] to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
          ></div>

          <div class="flex justify-between items-start mb-4">
            <h3
              class="text-4xl md:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-br from-gray-800 to-gray-500 dark:from-white dark:to-gray-500 group-hover:from-green-600 group-hover:to-green-400 dark:group-hover:from-[#9DC183] dark:group-hover:to-emerald-200 transition-all duration-500"
            >
              02<span class="text-2xl text-green-500 dark:text-[#9DC183]"
                >+</span
              >
            </h3>
            <div
              class="p-2.5 rounded-xl bg-gray-100 dark:bg-white/5 text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-500"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1.5"
                  d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"
                ></path>
              </svg>
            </div>
          </div>
          <p
            class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mt-2"
          >
            Klien & Mitra Puas
          </p>
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

// Deteksi Light/Dark mode untuk pattern grid
const isDark = ref(document.documentElement.classList.contains("dark"));

onMounted(() => {
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  gsap.to(".about-el", {
    scrollTrigger: { trigger: "#about", start: "top 75%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  gsap.to(".about-code-container", {
    scrollTrigger: { trigger: "#about", start: "top 70%" },
    x: 0,
    opacity: 1,
    duration: 1,
    ease: "power3.out",
  });

  gsap.to(".about-card", {
    scrollTrigger: { trigger: ".about-code-container", start: "top 60%" },
    y: 0,
    opacity: 1,
    duration: 0.6,
    stagger: 0.15,
    ease: "power3.out",
  });
});
</script>

<style scoped>
.about-el {
  transform: translateY(30px);
}
.about-card {
  transform: translateY(20px);
}

/* Grid Pattern (Opacity ditingkatkan agar lebih terlihat di Dark Mode) */
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
