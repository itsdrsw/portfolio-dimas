<template>
  <div class="bg-white dark:bg-gray-900 transition-colors duration-300">
    <!-- Contact Section -->
    <section id="contact" class="py-24">
      <div class="max-w-6xl mx-auto px-6">
        <!-- Header -->
        <div class="text-center mb-16 contact-header opacity-0">
          <h2
            class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4"
          >
            Mari Berkolaborasi
          </h2>
          <div
            class="w-16 h-1 bg-blue-600 dark:bg-blue-500 mx-auto rounded-full mb-6"
          ></div>
          <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">
            Tertarik untuk bekerja sama, memiliki pertanyaan seputar proyek,
            atau sekadar ingin menyapa? Jangan ragu untuk menghubungi saya.
          </p>
        </div>

        <div class="flex flex-col lg:flex-row gap-12 lg:gap-20">
          <!-- Informasi Kontak (Kiri) -->
          <div class="w-full lg:w-5/12 contact-info opacity-0">
            <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-6">
              Hubungi Saya Langsung
            </h3>

            <div class="space-y-6">
              <!-- Email -->
              <a
                href="mailto:dimasdharmasetiawan25@gmail.com"
                class="flex items-center group"
              >
                <div
                  class="w-12 h-12 bg-blue-50 dark:bg-gray-800 text-blue-600 dark:text-blue-400 rounded-lg flex items-center justify-center mr-4 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300"
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
                      stroke-width="2"
                      d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                    ></path>
                  </svg>
                </div>
                <div>
                  <p class="text-sm text-gray-500 dark:text-gray-400">Email</p>
                  <p
                    class="text-gray-900 dark:text-gray-200 font-medium group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors"
                  >
                    dimasdharmasetiawan25@gmail.com
                  </p>
                </div>
              </a>

              <!-- WhatsApp -->
              <a
                href="https://wa.me/6282389422820"
                target="_blank"
                class="flex items-center group"
              >
                <div
                  class="w-12 h-12 bg-blue-50 dark:bg-gray-800 text-blue-600 dark:text-blue-400 rounded-lg flex items-center justify-center mr-4 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300"
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
                      stroke-width="2"
                      d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
                    ></path>
                  </svg>
                </div>
                <div>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    WhatsApp / Telepon
                  </p>
                  <p
                    class="text-gray-900 dark:text-gray-200 font-medium group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors"
                  >
                    +62 823 8942 2820
                  </p>
                </div>
              </a>

              <!-- LinkedIn -->
              <a
                href="https://linkedin.com/in/dimas-dharma-setiawan"
                target="_blank"
                class="flex items-center group"
              >
                <div
                  class="w-12 h-12 bg-blue-50 dark:bg-gray-800 text-blue-600 dark:text-blue-400 rounded-lg flex items-center justify-center mr-4 group-hover:bg-blue-600 group-hover:text-white transition-colors duration-300"
                >
                  <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                    <path
                      d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                    />
                  </svg>
                </div>
                <div>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    LinkedIn
                  </p>
                  <p
                    class="text-gray-900 dark:text-gray-200 font-medium group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors"
                  >
                    Dimas Dharma Setiawan
                  </p>
                </div>
              </a>
            </div>
          </div>

          <!-- Formulir Kontak (Kanan) -->
          <div class="w-full lg:w-7/12 contact-form opacity-0">
            <div
              class="bg-gray-50 dark:bg-gray-800 p-8 rounded-2xl border border-gray-100 dark:border-gray-700 shadow-sm"
            >
              <form @submit.prevent="submitForm">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                  <div>
                    <label
                      class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
                      >Nama Lengkap</label
                    >
                    <input
                      type="text"
                      class="w-full px-4 py-3 bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 text-gray-900 dark:text-white transition-colors"
                      placeholder="Masukkan nama Anda"
                      required
                    />
                  </div>
                  <div>
                    <label
                      class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
                      >Email</label
                    >
                    <input
                      type="email"
                      class="w-full px-4 py-3 bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 text-gray-900 dark:text-white transition-colors"
                      placeholder="Masukkan email Anda"
                      required
                    />
                  </div>
                </div>
                <div class="mb-6">
                  <label
                    class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
                    >Pesan</label
                  >
                  <textarea
                    rows="4"
                    class="w-full px-4 py-3 bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 text-gray-900 dark:text-white transition-colors resize-none"
                    placeholder="Tuliskan pesan atau penawaran kerja sama..."
                    required
                  ></textarea>
                </div>
                <button
                  type="submit"
                  class="w-full py-3 px-6 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-lg transition-colors duration-300 shadow-lg shadow-blue-500/30"
                >
                  Kirim Pesan
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer Mungil di Bawah -->
    <footer
      class="bg-gray-100 dark:bg-gray-950 border-t border-gray-200 dark:border-gray-900 py-8 transition-colors duration-300"
    >
      <div class="max-w-6xl mx-auto px-6 text-center">
        <p class="text-gray-500 dark:text-gray-400 text-sm">
          &copy; {{ new Date().getFullYear() }} Dimas Dharma Setiawan. All
          rights reserved.
        </p>
        <p class="text-gray-400 dark:text-gray-600 text-xs mt-2">
          Dibangun dengan Vue 3, Tailwind CSS, dan animasi GSAP.
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

// Fungsi dummy untuk mencegah form refresh halaman saat disubmit (bisa Anda sambungkan ke API backend nantinya)
const submitForm = () => {
  alert(
    "Terima kasih! Pesan ini akan dihubungkan ke backend (misalnya via Formspree atau API Laravel Anda).",
  );
};

onMounted(() => {
  // Timeline Animasi GSAP
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: "#contact",
      start: "top 75%",
    },
  });

  tl.to(".contact-header", {
    y: 0,
    opacity: 1,
    duration: 0.8,
    ease: "power3.out",
  })
    .fromTo(
      ".contact-info",
      { x: -30, opacity: 0 },
      { x: 0, opacity: 1, duration: 0.8, ease: "power3.out" },
      "-=0.4",
    )
    .fromTo(
      ".contact-form",
      { x: 30, opacity: 0 },
      { x: 0, opacity: 1, duration: 0.8, ease: "power3.out" },
      "-=0.6",
    );
});
</script>

<style scoped>
.contact-header {
  transform: translateY(30px);
}
</style>
