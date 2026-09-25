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
              >Tentang Saya</span
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

      <!-- Baris Bawah: Kartu Metadata Personal -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-5 mt-16 lg:mt-24">
        <div
          class="about-card opacity-0 flex items-center gap-4 p-4 rounded-xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-sm hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 group shadow-sm"
        >
          <div
            class="w-10 h-10 rounded-lg bg-green-50 dark:bg-[#9DC183]/10 flex items-center justify-center text-green-600 dark:text-[#9DC183] group-hover:scale-110 transition-transform duration-300"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="1.5"
                d="M12 14l9-5-9-5-9 5 9 5z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="1.5"
                d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222"
              />
            </svg>
          </div>
          <div class="flex flex-col">
            <span
              class="text-[11px] font-bold text-gray-500 dark:text-gray-500 uppercase tracking-widest"
              >Pendidikan</span
            >
            <span class="text-sm font-medium text-gray-900 dark:text-gray-200"
              >Teknik Informatika</span
            >
          </div>
        </div>

        <div
          class="about-card opacity-0 flex items-center gap-4 p-4 rounded-xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-sm hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 group shadow-sm"
        >
          <div
            class="w-10 h-10 rounded-lg bg-green-50 dark:bg-[#9DC183]/10 flex items-center justify-center text-green-600 dark:text-[#9DC183] group-hover:scale-110 transition-transform duration-300"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="1.5"
                d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
              />
            </svg>
          </div>
          <div class="flex flex-col">
            <span
              class="text-[11px] font-bold text-gray-500 dark:text-gray-500 uppercase tracking-widest"
              >Fokus Utama</span
            >
            <span class="text-sm font-medium text-gray-900 dark:text-gray-200"
              >Web & Mobile</span
            >
          </div>
        </div>

        <div
          class="about-card opacity-0 flex items-center gap-4 p-4 rounded-xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-sm hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 group shadow-sm"
        >
          <div
            class="w-10 h-10 rounded-lg bg-green-50 dark:bg-[#9DC183]/10 flex items-center justify-center text-green-600 dark:text-[#9DC183] group-hover:scale-110 transition-transform duration-300"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="1.5"
                d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"
              />
            </svg>
          </div>
          <div class="flex flex-col">
            <span
              class="text-[11px] font-bold text-gray-500 dark:text-gray-500 uppercase tracking-widest"
              >Spesialisasi</span
            >
            <span class="text-sm font-medium text-gray-900 dark:text-gray-200"
              >Machine Learning</span
            >
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
