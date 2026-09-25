<template>
  <!-- Background menyesuaikan Light (gray-50) dan Dark (#080B09) -->
  <section
    id="home"
    class="relative min-h-screen flex items-center bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 overflow-hidden pt-20 pb-12 font-sans selection:bg-[#9DC183] selection:text-[#080B09]"
  >
    <!-- Pattern Grid Halus (Dinamis Light/Dark) -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow Lembut di belakang elemen 3D -->
    <div
      class="absolute top-1/2 left-1/2 lg:left-3/4 -translate-x-1/2 -translate-y-1/2 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-green-400 dark:bg-[#9DC183] opacity-[0.1] blur-[80px] md:blur-[120px] rounded-full pointer-events-none transition-colors duration-500"
    ></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6 w-full">
      <div
        class="grid grid-cols-1 lg:grid-cols-12 gap-16 lg:gap-8 items-center"
      >
        <!-- Kolom Kiri: Teks & Tipografi (7 Kolom) -->
        <div
          class="lg:col-span-7 order-2 lg:order-1 flex flex-col items-start text-left hero-text-container"
        >
          <span
            class="hero-el uppercase tracking-[0.25em] text-xs md:text-sm text-gray-500 dark:text-gray-400 mb-5 font-semibold transition-colors"
          >
            Halo, Saya
          </span>

          <h1
            class="hero-el text-4xl md:text-6xl lg:text-7xl font-extrabold text-gray-900 dark:text-white mb-4 leading-[1.1] tracking-tight transition-colors"
          >
            DIMAS DHARMA<br />SETIAWAN
          </h1>

          <!-- Aksen Sage Green di Dark Mode, Hijau Daun di Light Mode -->
          <h2
            class="hero-el text-xl md:text-3xl text-green-600 dark:text-[#9DC183] font-medium mb-6 tracking-wide transition-colors"
          >
            Software Developer
          </h2>

          <p
            class="hero-el text-gray-600 dark:text-gray-400 text-base md:text-lg max-w-lg mb-10 leading-relaxed font-light transition-colors"
          >
            Saya membangun aplikasi web, aplikasi mobile, dan solusi machine
            learning.
          </p>

          <div class="hero-el flex flex-col sm:flex-row gap-5 w-full sm:w-auto">
            <a
              href="#projects"
              class="px-8 py-3.5 bg-green-600 dark:bg-[#9DC183] text-white dark:text-[#080B09] font-bold rounded-lg hover:bg-green-700 dark:hover:bg-[#8ab36f] transition-all duration-300 flex items-center justify-center gap-2 text-sm tracking-wide shadow-lg shadow-green-500/20 dark:shadow-[#9DC183]/10"
            >
              LIHAT PROYEK
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
                  d="M14 5l7 7m0 0l-7 7m7-7H3"
                ></path>
              </svg>
            </a>

            <a
              href="#contact"
              class="px-8 py-3.5 bg-transparent border border-gray-300 dark:border-gray-700 text-gray-700 dark:text-white font-semibold rounded-lg hover:border-green-600 dark:hover:border-[#9DC183] hover:text-green-600 dark:hover:text-[#9DC183] transition-all duration-300 flex items-center justify-center text-sm tracking-wide"
            >
              HUBUNGI SAYA
            </a>
          </div>
        </div>

        <!-- Kolom Kanan: 3D Anti-Gravity Icons (5 Kolom) -->
        <div
          class="lg:col-span-5 order-1 lg:order-2 flex justify-center items-center relative min-h-[350px]"
        >
          <!-- Container Utama Ikon (Ganti img src dengan gambar 3D Anda nanti) -->
          <div
            class="floating-main relative z-20 w-48 h-48 md:w-64 md:h-64 flex items-center justify-center"
          >
            <!-- Placeholder Ikon Tengah (Code) -->
            <div
              class="w-full h-full bg-gradient-to-tr from-green-500 to-blue-500 dark:from-[#9DC183] dark:to-[#4e6b3c] rounded-3xl shadow-2xl flex items-center justify-center transform rotate-12 backdrop-blur-xl border border-white/20"
            >
              <svg
                class="w-24 h-24 text-white drop-shadow-lg"
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

            <!-- Anda bisa mengganti div di atas dengan tag img seperti ini: -->
            <!-- <img src="/3d-coding-icon.png" alt="3D Code Icon" class="w-full h-full object-contain drop-shadow-2xl" /> -->
          </div>

          <!-- Elemen Melayang Kecil (Kiri Atas) -->
          <div
            class="floating-slow absolute top-10 left-10 md:left-4 z-30 w-16 h-16 bg-white dark:bg-gray-800 rounded-2xl shadow-xl flex items-center justify-center border border-gray-100 dark:border-gray-700"
          >
            <svg
              class="w-8 h-8 text-blue-500"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zm6.93 6h-2.95a15.65 15.65 0 00-1.38-3.56A8.03 8.03 0 0118.92 8zM12 4.04c.83 1.2 1.48 2.53 1.91 3.96h-3.82c.43-1.43 1.08-2.76 1.91-3.96zM4.26 14C4.1 13.36 4 12.69 4 12s.1-1.36.26-2h3.38c-.08.66-.14 1.32-.14 2s.06 1.34.14 2H4.26zm.82 2h2.95c.32 1.25.78 2.45 1.38 3.56A7.987 7.987 0 015.08 16zm2.95-8H5.08a7.987 7.987 0 013.9-3.56C8.38 5.55 7.92 6.75 7.6 8zm4.4 11.96c-.83-1.2-1.48-2.53-1.91-3.96h3.82c-.43 1.43-1.08 2.76-1.91 3.96zM14.34 14H9.66c-.09-.66-.16-1.32-.16-2s.07-1.34.16-2h4.68c.09.66.16 1.32.16 2s-.07 1.34-.16 2zm1.18 5.56c.6-1.11 1.06-2.31 1.38-3.56h2.95a8.03 8.03 0 01-4.33 3.56zM16.36 14c.08-.66.14-1.32.14-2s-.06-1.34-.14-2h3.38c.16.64.26 1.31.26 2s-.1 1.36-.26 2h-3.38z"
              />
            </svg>
          </div>

          <!-- Elemen Melayang Kecil (Kanan Bawah) -->
          <div
            class="floating-fast absolute bottom-12 right-12 md:right-0 z-30 px-5 py-2.5 bg-white/90 dark:bg-gray-800/90 backdrop-blur-md rounded-full shadow-lg border border-gray-100 dark:border-gray-700"
          >
            <span
              class="text-green-600 dark:text-[#9DC183] text-xs font-bold tracking-[0.1em]"
              >AI & ML</span
            >
          </div>
        </div>
      </div>
    </div>

    <!-- Indikator Scroll Vertikal -->
    <div
      class="absolute bottom-6 left-1/2 -translate-x-1/2 flex flex-col items-center gap-3 opacity-50 hover:opacity-100 transition-opacity duration-300 cursor-pointer scroll-indicator hidden sm:flex"
    >
      <span
        class="text-[9px] tracking-[0.3em] text-gray-500 dark:text-gray-400 font-semibold uppercase"
        >Scroll</span
      >
      <div
        class="w-[1px] h-8 bg-gradient-to-b from-gray-400 dark:from-gray-500 to-transparent"
      ></div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";

// Mengecek status mode gelap di document
const isDark = ref(document.documentElement.classList.contains("dark"));

// Observer untuk mendeteksi perubahan dark/light mode agar pattern grid ikut berubah
onMounted(() => {
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  // Animasi masuk awal (Entry Animation)
  const tl = gsap.timeline({ delay: 0.2 });

  tl.from(".hero-el", {
    y: 40,
    opacity: 0,
    duration: 1,
    stagger: 0.15,
    ease: "power3.out",
  })
    .from(
      ".floating-main, .floating-slow, .floating-fast",
      {
        scale: 0.8,
        opacity: 0,
        duration: 1.5,
        stagger: 0.2,
        ease: "back.out(1.5)",
      },
      "-=0.8",
    )
    .from(
      ".scroll-indicator",
      {
        opacity: 0,
        duration: 1,
      },
      "-=0.5",
    );

  // Animasi Anti-Gravity (Melayang terus menerus)
  // Ikon utama bergerak lembut
  gsap.to(".floating-main", {
    y: -20,
    rotation: 10, // Tambahan efek memutar sangat pelan
    duration: 4,
    ease: "sine.inOut",
    yoyo: true,
    repeat: -1,
  });

  // Ikon kecil atas bergerak berlawanan
  gsap.to(".floating-slow", {
    y: 15,
    duration: 3.5,
    ease: "sine.inOut",
    yoyo: true,
    repeat: -1,
    delay: 0.5, // Delay agar tidak searah dengan ikon utama
  });

  // Ikon kecil bawah (pill AI & ML) bergerak lebih cepat
  gsap.to(".floating-fast", {
    y: -12,
    x: 5,
    duration: 2.5,
    ease: "sine.inOut",
    yoyo: true,
    repeat: -1,
    delay: 1,
  });
});
</script>

<style scoped>
/* CSS untuk menciptakan pola grid dinamis Light/Dark */
.bg-grid-dark {
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.04) 1px, transparent 1px);
  background-size: 40px 40px;
}
.bg-grid-light {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
}
</style>
