<template>
  <!-- bg-gray-50 memberikan sedikit perbedaan warna dari Hero/Skills agar ada batasan visual yang jelas -->
  <section
    id="about"
    class="py-24 bg-gray-100 dark:bg-gray-900/50 transition-colors duration-300 overflow-hidden"
  >
    <div class="max-w-6xl mx-auto px-6">
      <div class="flex flex-col md:flex-row items-center gap-12 lg:gap-20">
        <!-- Kolom Gambar/Ilustrasi (Kiri) -->
        <div class="w-full md:w-5/12 about-img opacity-0 -translate-x-12">
          <!-- Kotak placeholder ini nanti bisa Anda ganti dengan tag <img> berisi pasfoto formal/santai Anda -->
          <div
            class="aspect-square bg-blue-100 dark:bg-gray-800 rounded-3xl overflow-hidden relative shadow-xl border border-gray-200 dark:border-gray-700 transform rotate-3 hover:rotate-0 transition-transform duration-500"
          >
            <div
              class="absolute inset-0 flex items-center justify-center text-gray-400 dark:text-gray-500 font-medium"
            >
              [Foto Profil Anda]
            </div>
          </div>
        </div>

        <!-- Kolom Teks (Kanan) -->
        <div class="w-full md:w-7/12 about-text opacity-0 translate-x-12">
          <div
            class="inline-block px-4 py-1 mb-4 rounded-full bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-400 text-sm font-semibold tracking-wide"
          >
            Tentang Saya
          </div>

          <h2
            class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-6"
          >
            Menghubungkan Rekayasa Perangkat Lunak & Kecerdasan Buatan
          </h2>

          <p
            class="text-gray-600 dark:text-gray-400 text-lg mb-4 leading-relaxed"
          >
            Saya adalah lulusan D4 Teknik Informatika[cite: 1] yang memiliki
            ketertarikan mendalam pada eksplorasi solusi digital yang akurat dan
            terukur. Selama masa studi, saya banyak mengambil studi kasus nyata,
            mulai dari merancang aplikasi <i>end-to-end</i> untuk
            mendigitalisasi operasional UMKM lokal hingga memproses dataset
            rekam medis menggunakan <i>Machine Learning</i>[cite: 1].
          </p>

          <p
            class="text-gray-600 dark:text-gray-400 text-lg mb-8 leading-relaxed"
          >
            Berbekal ilmu dari praktisi di bidang
            <i>Software Quality Assurance</i> (SQA) dan pengalaman kolaborasi
            lintas peran[cite: 1], saya selalu memastikan setiap sistem yang
            dibangun tidak hanya berfungsi dengan baik secara teknis, tetapi
            juga memberikan pengalaman pengguna yang intuitif dan mudah
            dipelihara.
          </p>

          <!-- Info Singkat -->
          <div
            class="grid grid-cols-2 gap-6 pt-6 border-t border-gray-200 dark:border-gray-800"
          >
            <div>
              <span
                class="block text-sm text-gray-500 dark:text-gray-500 uppercase tracking-wider mb-1"
                >Pendidikan Utama</span
              >
              <span class="text-gray-900 dark:text-gray-200 font-semibold"
                >D4 Teknik Informatika[cite: 1]</span
              >
            </div>
            <div>
              <span
                class="block text-sm text-gray-500 dark:text-gray-500 uppercase tracking-wider mb-1"
                >Fokus Pengembangan</span
              >
              <span class="text-gray-900 dark:text-gray-200 font-semibold"
                >Full-stack Web & AI[cite: 1]</span
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  // Timeline GSAP untuk menganimasikan gambar dan teks secara bersamaan namun dari arah berlawanan
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: "#about",
      start: "top 75%", // Animasi mulai saat elemen mencapai 75% dari atas viewport
    },
  });

  // Gambar masuk dari kiri
  tl.to(
    ".about-img",
    {
      x: 0,
      opacity: 1,
      duration: 0.9,
      ease: "power3.out",
    },
    0,
  ) // Angka 0 di akhir berarti mulai di detik ke-0 pada timeline ini

    // Teks masuk dari kanan di waktu yang sama
    .to(
      ".about-text",
      {
        x: 0,
        opacity: 1,
        duration: 0.9,
        ease: "power3.out",
      },
      0,
    );
});
</script>
