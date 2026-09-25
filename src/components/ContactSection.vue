<template>
  <!-- Wrapper luar menggunakan warna bg persis seperti section sebelumnya -->
  <div
    class="relative bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 font-sans overflow-hidden"
  >
    <!-- Pattern Grid Halus -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow di KIRI (Melanjutkan zig-zag dari Projects yang di kanan) -->
    <div
      class="absolute top-1/3 -left-32 md:-left-48 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-green-400 dark:bg-[#9DC183] opacity-[0.05] blur-[100px] md:blur-[120px] rounded-full pointer-events-none z-0 transition-colors duration-500"
    ></div>

    <section id="contact" class="py-24 relative z-10">
      <div class="max-w-7xl mx-auto px-6">
        <!-- Header -->
        <div class="mb-20 text-center flex flex-col items-center">
          <div class="flex items-center gap-4 mb-4 contact-header-el opacity-0">
            <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
            <span
              class="uppercase tracking-[0.2em] text-xs font-bold text-gray-500 dark:text-gray-400"
              >Contact</span
            >
            <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
          </div>
          <h2
            class="text-3xl md:text-5xl font-extrabold text-gray-900 dark:text-white mb-6 leading-[1.2] tracking-tight contact-header-el opacity-0"
          >
            Mulai Percakapan.
          </h2>
          <p
            class="text-gray-600 dark:text-gray-400 text-base md:text-lg max-w-2xl leading-relaxed font-light contact-header-el opacity-0"
          >
            Tertarik untuk bekerja sama, memiliki pertanyaan seputar proyek,
            atau sekadar ingin menyapa? Saya selalu terbuka untuk mendiskusikan
            peluang baru.
          </p>
        </div>

        <div
          class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-16 items-start"
        >
          <!-- Informasi Kontak (Kiri - 5 Kolom) -->
          <div class="lg:col-span-5 flex flex-col gap-6">
            <!-- Email Card (Warna disamakan dengan Project Card) -->
            <a
              href="mailto:dimasdharmasetiawan25@gmail.com"
              class="contact-info-card opacity-0 group flex items-center p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/60 dark:bg-white/[0.015] backdrop-blur-md hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl hover:shadow-green-500/5"
            >
              <div
                class="w-14 h-14 rounded-xl bg-gray-100 dark:bg-white/[0.03] border border-gray-200 dark:border-white/10 flex items-center justify-center text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-300 mr-5"
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
                    d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                  ></path>
                </svg>
              </div>
              <div>
                <p
                  class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-1"
                >
                  Email
                </p>
                <p
                  class="text-sm md:text-base font-semibold text-gray-900 dark:text-gray-200 group-hover:text-green-600 dark:group-hover:text-[#9DC183] transition-colors break-all"
                >
                  dimasdharmasetiawan25@gmail.com
                </p>
              </div>
            </a>

            <!-- WhatsApp Card -->
            <a
              href="https://wa.me/6282389422820"
              target="_blank"
              class="contact-info-card opacity-0 group flex items-center p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/60 dark:bg-white/[0.015] backdrop-blur-md hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl hover:shadow-green-500/5"
            >
              <div
                class="w-14 h-14 rounded-xl bg-gray-100 dark:bg-white/[0.03] border border-gray-200 dark:border-white/10 flex items-center justify-center text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-300 mr-5"
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
                    d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
                  ></path>
                </svg>
              </div>
              <div>
                <p
                  class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-1"
                >
                  WhatsApp
                </p>
                <p
                  class="text-sm md:text-base font-semibold text-gray-900 dark:text-gray-200 group-hover:text-green-600 dark:group-hover:text-[#9DC183] transition-colors"
                >
                  +62 823 8942 2820
                </p>
              </div>
            </a>

            <!-- LinkedIn Card -->
            <a
              href="https://linkedin.com/in/dimas-dharma-setiawan"
              target="_blank"
              class="contact-info-card opacity-0 group flex items-center p-6 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/60 dark:bg-white/[0.015] backdrop-blur-md hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl hover:shadow-green-500/5"
            >
              <div
                class="w-14 h-14 rounded-xl bg-gray-100 dark:bg-white/[0.03] border border-gray-200 dark:border-white/10 flex items-center justify-center text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-300 mr-5"
              >
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                  />
                </svg>
              </div>
              <div>
                <p
                  class="text-[11px] font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-1"
                >
                  LinkedIn
                </p>
                <p
                  class="text-sm md:text-base font-semibold text-gray-900 dark:text-gray-200 group-hover:text-green-600 dark:group-hover:text-[#9DC183] transition-colors"
                >
                  Dimas Dharma Setiawan
                </p>
              </div>
            </a>
          </div>

          <!-- Formulir Kontak (Kanan - 7 Kolom) -->
          <div class="lg:col-span-7 contact-form-el opacity-0">
            <!-- Box Utama Form disamakan dengan Project Card -->
            <div
              class="p-8 md:p-10 rounded-3xl border border-gray-200 dark:border-white/5 bg-white/60 dark:bg-white/[0.015] backdrop-blur-md shadow-2xl relative overflow-hidden"
            >
              <!-- Aksen garis halus di atas form -->
              <div
                class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-green-500 dark:via-[#9DC183] to-transparent opacity-50"
              ></div>

              <form @submit.prevent="submitForm">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                  <div>
                    <label
                      class="block text-xs font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-2"
                      >Nama Lengkap</label
                    >
                    <!-- Input background dibuat lebih gelap sedikit (black/20) untuk kontras di dalam box form -->
                    <input
                      type="text"
                      class="w-full px-5 py-3.5 bg-white dark:bg-black/20 border border-gray-200 dark:border-white/10 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500/50 dark:focus:ring-[#9DC183]/50 focus:border-green-500 dark:focus:border-[#9DC183] text-gray-900 dark:text-white transition-all placeholder-gray-400 dark:placeholder-gray-600 text-sm"
                      placeholder="Masukkan nama Anda"
                      required
                    />
                  </div>
                  <div>
                    <label
                      class="block text-xs font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-2"
                      >Email</label
                    >
                    <input
                      type="email"
                      class="w-full px-5 py-3.5 bg-white dark:bg-black/20 border border-gray-200 dark:border-white/10 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500/50 dark:focus:ring-[#9DC183]/50 focus:border-green-500 dark:focus:border-[#9DC183] text-gray-900 dark:text-white transition-all placeholder-gray-400 dark:placeholder-gray-600 text-sm"
                      placeholder="email@domain.com"
                      required
                    />
                  </div>
                </div>
                <div class="mb-8">
                  <label
                    class="block text-xs font-bold text-gray-500 dark:text-gray-400 uppercase tracking-widest mb-2"
                    >Pesan</label
                  >
                  <textarea
                    rows="5"
                    class="w-full px-5 py-3.5 bg-white dark:bg-black/20 border border-gray-200 dark:border-white/10 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500/50 dark:focus:ring-[#9DC183]/50 focus:border-green-500 dark:focus:border-[#9DC183] text-gray-900 dark:text-white transition-all placeholder-gray-400 dark:placeholder-gray-600 text-sm resize-none"
                    placeholder="Tuliskan pesan atau penawaran kerja sama..."
                    required
                  ></textarea>
                </div>

                <button
                  type="submit"
                  class="w-full sm:w-auto px-8 py-4 bg-green-600 dark:bg-[#9DC183] text-white dark:text-[#080B09] font-bold rounded-xl hover:bg-green-700 dark:hover:bg-[#8ab36f] transition-all duration-300 flex items-center justify-center gap-2 text-sm tracking-wide shadow-lg shadow-green-500/20 dark:shadow-[#9DC183]/10 cursor-pointer"
                >
                  KIRIM PESAN
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer Terintegrasi (Background Transparan Menyatu dengan Section) -->
    <footer
      class="relative z-10 border-t border-gray-200 dark:border-white/5 py-10 mt-12"
    >
      <div
        class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center gap-4"
      >
        <div class="text-center md:text-left">
          <a
            href="#"
            class="text-xl font-bold text-gray-900 dark:text-white tracking-wide block mb-1"
          >
            Portfolio<span class="text-green-600 dark:text-[#9DC183]">
              itsdrsw</span
            >
          </a>
          <p class="text-gray-500 dark:text-gray-500 text-xs font-medium">
            &copy; 2026 Dimas Dharma Setiawan. Hak Cipta Dilindungi.
          </p>
        </div>

        <div class="flex items-center gap-6">
          <a
            href="https://github.com/dimasdharmasetiawan"
            target="_blank"
            class="text-gray-400 hover:text-green-600 dark:hover:text-[#9DC183] transition-colors cursor-pointer"
          >
            <span class="sr-only">GitHub</span>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                fill-rule="evenodd"
                d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </a>
          <a
            href="#"
            class="text-gray-400 hover:text-green-600 dark:hover:text-[#9DC183] transition-colors cursor-pointer"
            @click.prevent="scrollToTop"
          >
            <span class="text-xs font-bold uppercase tracking-widest"
              >Kembali ke Atas ↑</span
            >
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const isDark = ref(false);

const submitForm = () => {
  alert("Terima kasih! Pesan Anda siap untuk diintegrasikan dengan backend.");
};

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
};

onMounted(() => {
  isDark.value = document.documentElement.classList.contains("dark");
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  gsap.to(".contact-header-el", {
    scrollTrigger: { trigger: "#contact", start: "top 85%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  gsap.to(".contact-info-card", {
    scrollTrigger: { trigger: ".contact-info-card", start: "top 80%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  gsap.to(".contact-form-el", {
    scrollTrigger: { trigger: ".contact-form-el", start: "top 75%" },
    y: 0,
    opacity: 1,
    duration: 1,
    ease: "power3.out",
    delay: 0.2,
  });
});
</script>

<style scoped>
.contact-header-el {
  transform: translateY(30px);
}
.contact-info-card {
  transform: translateY(30px);
}
.contact-form-el {
  transform: translateY(50px);
}

/* Pola Grid persis seperti Projects dan Experience */
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
