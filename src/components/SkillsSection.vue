<template>
  <section
    id="skills"
    class="py-24 bg-white dark:bg-gray-900 transition-colors duration-300"
  >
    <div class="max-w-6xl mx-auto px-6">
      <!-- Judul Section -->
      <div class="text-center mb-16 skill-header opacity-0">
        <h2
          class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4"
        >
          Keahlian & Teknologi
        </h2>
        <div
          class="w-16 h-1 bg-blue-600 dark:bg-blue-500 mx-auto rounded-full"
        ></div>
      </div>

      <!-- Grid Keahlian -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Looping Kategori Keahlian -->
        <div
          v-for="(category, index) in skills"
          :key="index"
          class="skill-card opacity-0 bg-gray-50 dark:bg-gray-800 rounded-xl p-6 border border-gray-100 dark:border-gray-700 shadow-sm hover:shadow-md transition-shadow"
        >
          <div class="flex items-center mb-4 space-x-3">
            <span class="text-2xl">{{ category.icon }}</span>
            <h3 class="text-xl font-semibold text-gray-800 dark:text-gray-200">
              {{ category.title }}
            </h3>
          </div>

          <div class="flex flex-wrap gap-2">
            <span
              v-for="(tech, idx) in category.items"
              :key="idx"
              class="px-3 py-1 bg-white dark:bg-gray-900 text-gray-600 dark:text-gray-300 text-sm font-medium rounded-full border border-gray-200 dark:border-gray-700"
            >
              {{ tech }}
            </span>
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

// Registrasi ScrollTrigger agar bisa digunakan
gsap.registerPlugin(ScrollTrigger);

// Data Keahlian berdasarkan CV Anda
const skills = ref([
  {
    title: "Frontend Development",
    icon: "💻",
    items: [
      "React Vite",
      "Vue.js",
      "Tailwind CSS",
      "Bootstrap",
      "JavaScript",
      "CSS",
    ],
  },
  {
    title: "Backend & API",
    icon: "⚙️",
    items: ["PHP", "Laravel", "Node.js", "REST API"],
  },
  {
    title: "Database Management",
    icon: "🗄️",
    items: ["MySQL", "PostgreSQL", "Supabase"],
  },
  {
    title: "Data & Machine Learning",
    icon: "🤖",
    items: ["Python", "Scikit-learn", "Pandas", "Computer Vision"],
  },
  {
    title: "Tools & Sistem",
    icon: "🛠️",
    items: ["Odoo ERP", "Git / GitHub", "VS Code", "Linux Terminal", "Figma"],
  },
]);

onMounted(() => {
  // 1. Animasi Judul saat di-scroll
  gsap.to(".skill-header", {
    scrollTrigger: {
      trigger: "#skills",
      start: "top 80%", // Animasi mulai saat bagian atas section mencapai 80% dari tinggi layar
    },
    y: 0,
    opacity: 1,
    duration: 0.8,
    ease: "power3.out",
  });

  // 2. Animasi Kartu Keahlian (Berurutan / Stagger)
  gsap.to(".skill-card", {
    scrollTrigger: {
      trigger: ".skill-header",
      start: "top 70%",
    },
    y: -20, // Bergerak naik sedikit
    opacity: 1,
    duration: 0.6,
    stagger: 0.15, // Jeda waktu antar kartu
    ease: "back.out(1.7)", // Efek memantul (bouncing) sedikit di akhir gerakan
  });
});
</script>
