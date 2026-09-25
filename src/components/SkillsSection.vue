<template>
  <section
    id="skills"
    class="relative py-24 bg-gray-50 dark:bg-[#080B09] transition-colors duration-500 font-sans overflow-hidden"
  >
    <!-- Pattern Grid Halus yang berlanjut dari About (Dinamis Light/Dark) -->
    <div
      class="absolute inset-0 opacity-40 pointer-events-none"
      :class="isDark ? 'bg-grid-dark' : 'bg-grid-light'"
    ></div>

    <!-- Pendaran Glow di KANAN untuk transisi zig-zag dari About (Kiri) -->
    <div
      class="absolute top-1/2 right-0 lg:-right-32 -translate-y-1/2 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-green-400 dark:bg-[#9DC183] opacity-[0.05] blur-[100px] md:blur-[120px] rounded-full pointer-events-none z-0 transition-colors duration-500"
    ></div>

    <div class="max-w-7xl mx-auto px-6 relative z-10">
      <!-- Judul Section -->
      <div class="mb-16 md:mb-20">
        <div class="flex items-center gap-4 mb-4 skill-header-el opacity-0">
          <div class="w-8 h-[2px] bg-green-600 dark:bg-[#9DC183]"></div>
          <span
            class="uppercase tracking-[0.2em] text-xs font-bold text-gray-500 dark:text-gray-400"
            >Skills</span
          >
        </div>
        <h2
          class="text-3xl md:text-4xl lg:text-5xl font-extrabold text-gray-900 dark:text-white mb-6 leading-[1.2] tracking-tight skill-header-el opacity-0 max-w-2xl"
        >
          Keahlian & Ekosistem Teknologi
        </h2>
      </div>

      <!-- Grid Keahlian -->
      <div
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 lg:gap-8"
      >
        <div
          v-for="(category, index) in skills"
          :key="index"
          class="skill-card opacity-0 group p-7 rounded-2xl border border-gray-200 dark:border-white/5 bg-white/40 dark:bg-white/[0.02] backdrop-blur-md hover:bg-white/60 dark:hover:bg-white/[0.04] hover:border-green-400 dark:hover:border-[#9DC183]/40 transition-all duration-500 hover:-translate-y-2 hover:shadow-xl hover:shadow-green-500/5 flex flex-col h-full"
        >
          <!-- Header Kartu -->
          <div class="flex items-center gap-4 mb-8">
            <div
              class="w-12 h-12 rounded-xl bg-gray-100 dark:bg-white/[0.03] border border-gray-200 dark:border-white/10 flex items-center justify-center text-gray-500 dark:text-gray-400 group-hover:text-green-600 dark:group-hover:text-[#9DC183] group-hover:border-green-400 dark:group-hover:border-[#9DC183]/30 group-hover:bg-green-50 dark:group-hover:bg-[#9DC183]/10 transition-all duration-500"
            >
              <div v-html="category.categoryIcon" class="w-6 h-6"></div>
            </div>
            <h3
              class="text-xl font-bold text-gray-900 dark:text-gray-100 group-hover:text-green-600 dark:group-hover:text-white transition-colors"
            >
              {{ category.title }}
            </h3>
          </div>

          <!-- Grid Ikon Teknologi Berwarna (mt-auto dihapus agar posisi di atas) -->
          <div class="grid grid-cols-3 gap-y-6 gap-x-2">
            <div
              v-for="(tech, idx) in category.items"
              :key="idx"
              class="flex flex-col items-center justify-center gap-3 group/icon"
            >
              <!-- Class text-gray-800 dark:text-gray-200 ditambahkan agar ikon monokrom beradaptasi -->
              <Icon
                :icon="tech.icon"
                class="w-9 h-9 opacity-80 group-hover/icon:opacity-100 group-hover/icon:scale-110 transition-all duration-300 drop-shadow-md text-gray-800 dark:text-gray-200"
              />
              <span
                class="text-[11px] font-medium text-gray-600 dark:text-gray-500 group-hover/icon:text-green-600 dark:group-hover/icon:text-gray-300 text-center transition-colors"
              >
                {{ tech.name }}
              </span>
            </div>
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
import { Icon } from "@iconify/vue";

gsap.registerPlugin(ScrollTrigger);

// Deteksi Light/Dark mode
const isDark = ref(false);

const skills = ref([
  {
    title: "Frontend",
    categoryIcon:
      '<svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>',
    items: [
      { name: "React", icon: "skill-icons:react-dark" },
      { name: "Vue.js", icon: "skill-icons:vuejs-dark" },
      { name: "Tailwind", icon: "skill-icons:tailwindcss-dark" },
      { name: "Bootstrap", icon: "skill-icons:bootstrap" },
      { name: "JavaScript", icon: "skill-icons:javascript" },
      { name: "CSS", icon: "skill-icons:css" },
    ],
  },
  {
    title: "Backend & API",
    categoryIcon:
      '<svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"></path></svg>',
    items: [
      { name: "PHP", icon: "skill-icons:php-dark" },
      { name: "Laravel", icon: "skill-icons:laravel-dark" },
      { name: "Node.js", icon: "skill-icons:nodejs-dark" },
      { name: "Odoo", icon: "simple-icons:odoo" },
      { name: "REST API", icon: "carbon:api-1" },
    ],
  },
  {
    title: "Database",
    categoryIcon:
      '<svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4"></path></svg>',
    items: [
      { name: "MySQL", icon: "skill-icons:mysql-dark" },
      { name: "PostgreSQL", icon: "skill-icons:postgresql-dark" },
      { name: "Supabase", icon: "skill-icons:supabase-dark" },
    ],
  },
  {
    title: "Data & AI",
    categoryIcon:
      '<svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path></svg>',
    items: [
      { name: "Python", icon: "skill-icons:python-dark" },
      { name: "Scikit-learn", icon: "devicon:scikitlearn" },
      { name: "Pandas", icon: "simple-icons:pandas" },
      { name: "Computer Vision", icon: "carbon:machine-learning-model" },
    ],
  },
  {
    title: "Tools & Sistem",
    categoryIcon:
      '<svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065zM15 12a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>',
    items: [
      { name: "Docker", icon: "skill-icons:docker" },
      { name: "Git / GitHub", icon: "skill-icons:github-dark" },
      { name: "VS Code", icon: "skill-icons:vscode-dark" },
      { name: "Linux", icon: "skill-icons:linux-dark" },
      { name: "Cloudflare", icon: "skill-icons:cloudflare-dark" },
      { name: "Figma", icon: "skill-icons:figma-dark" },
    ],
  },
]);

onMounted(() => {
  // Setup Observer untuk merespons tombol Light/Dark mode
  isDark.value = document.documentElement.classList.contains("dark");
  const observer = new MutationObserver(() => {
    isDark.value = document.documentElement.classList.contains("dark");
  });
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ["class"],
  });

  // Animasi GSAP
  gsap.to(".skill-header-el", {
    scrollTrigger: { trigger: "#skills", start: "top 80%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.15,
    ease: "power3.out",
  });

  gsap.to(".skill-card", {
    scrollTrigger: { trigger: ".skill-header-el", start: "top 65%" },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.1,
    ease: "power3.out",
  });
});
</script>

<style scoped>
.skill-header-el {
  transform: translateY(30px);
}
.skill-card {
  transform: translateY(40px);
}

/* Pola Grid dengan Opacity 0.08 sesuai dengan About Section */
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
