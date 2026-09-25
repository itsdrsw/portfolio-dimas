<template>
  <!-- Navbar Fixed Base -->
  <nav
    :class="[
      'fixed top-0 left-0 w-full z-50 transition-all duration-500 font-sans',
      isScrolled
        ? 'bg-white/80 dark:bg-[#080B09]/80 backdrop-blur-lg border-b border-gray-200 dark:border-white/10 py-4 shadow-sm dark:shadow-none'
        : 'bg-transparent py-6',
    ]"
  >
    <div class="max-w-7xl mx-auto px-6 flex justify-between items-center">
      <!-- Kiri: Logo Wordmark -->
      <a
        href="#home"
        @click="scrollToSection($event, 'home')"
        class="text-xl md:text-2xl font-extrabold text-gray-900 dark:text-white tracking-wide group"
      >
        its<span
          class="text-green-600 dark:text-[#9DC183] transition-colors group-hover:text-green-500"
          >drsw.</span
        >
      </a>

      <!-- Tengah: Tautan Navigasi (Desktop) -->
      <ul class="hidden lg:flex items-center gap-8">
        <li v-for="(link, index) in navLinks" :key="index">
          <a
            :href="`#${link.id}`"
            @click="scrollToSection($event, link.id)"
            :class="[
              'text-sm font-semibold tracking-wide transition-all duration-300 relative py-2',
              activeSection === link.id
                ? 'text-green-600 dark:text-[#9DC183]'
                : 'text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white',
            ]"
          >
            {{ link.name }}
            <!-- Indikator Active (Garis Bawah Halus) -->
            <span
              class="absolute left-0 bottom-0 w-full h-[2px] bg-green-600 dark:bg-[#9DC183] transform origin-left transition-transform duration-300"
              :class="activeSection === link.id ? 'scale-x-100' : 'scale-x-0'"
            ></span>
          </a>
        </li>
      </ul>

      <!-- Kanan: Actions (Dark Mode Toggle & CTA & Hamburger) -->
      <div class="flex items-center gap-4 md:gap-6">
        <!-- Toggle Light/Dark Mode -->
        <button
          @click="toggleTheme"
          class="p-2 text-gray-500 dark:text-gray-400 hover:text-green-600 dark:hover:text-[#9DC183] hover:bg-gray-100 dark:hover:bg-white/5 rounded-full transition-all duration-300 focus:outline-none"
          aria-label="Toggle Dark Mode"
        >
          <!-- Ikon Matahari (Tampil saat Dark Mode aktif) -->
          <svg
            v-if="isDark"
            class="w-5 h-5"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
            ></path>
          </svg>
          <!-- Ikon Bulan (Tampil saat Light Mode aktif) -->
          <svg
            v-else
            class="w-5 h-5"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
            ></path>
          </svg>
        </button>

        <!-- Tombol Hamburger (Mobile) -->
        <button
          @click="isMobileMenuOpen = !isMobileMenuOpen"
          class="lg:hidden p-2 text-gray-900 dark:text-white focus:outline-none"
        >
          <svg
            v-if="!isMobileMenuOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
          </svg>
          <svg
            v-else
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu Dropdown (Full Width) -->
    <div
      class="lg:hidden absolute top-full left-0 w-full bg-white dark:bg-[#080B09] border-b border-gray-200 dark:border-white/10 transition-all duration-300 overflow-hidden shadow-xl"
      :class="
        isMobileMenuOpen ? 'max-h-[500px] opacity-100' : 'max-h-0 opacity-0'
      "
    >
      <ul class="flex flex-col px-6 py-4 space-y-4">
        <li v-for="(link, index) in navLinks" :key="index">
          <a
            :href="`#${link.id}`"
            @click="scrollToSection($event, link.id)"
            class="block text-base font-semibold transition-colors duration-300"
            :class="
              activeSection === link.id
                ? 'text-green-600 dark:text-[#9DC183]'
                : 'text-gray-600 dark:text-gray-400'
            "
          >
            {{ link.name }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

// State Management
const isScrolled = ref(false);
const isMobileMenuOpen = ref(false);
const isDark = ref(false);
const activeSection = ref("home");

// Definisi Navigasi
const navLinks = [
  { name: "Home", id: "home" },
  { name: "About Me", id: "about" },
  { name: "Skills", id: "skills" },
  { name: "Experience", id: "experience" },
  { name: "Projects", id: "projects" },
  { name: "Contact", id: "contact" },
];

// Handle Scroll untuk mengubah background Navbar
const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

// Smooth Scrolling & Close Mobile Menu
const scrollToSection = (e, targetId) => {
  e.preventDefault();
  isMobileMenuOpen.value = false; // Tutup menu mobile

  const targetElement = document.getElementById(targetId);
  if (targetElement) {
    // Kurangi tinggi navbar (sekitar 80px) agar judul section tidak tertutup
    const offset = 80;
    const elementPosition = targetElement.getBoundingClientRect().top;
    const offsetPosition = elementPosition + window.scrollY - offset;

    window.scrollTo({
      top: offsetPosition,
      behavior: "smooth",
    });
  }
};

// Toggle Tema (Light / Dark Mode)
const toggleTheme = () => {
  isDark.value = !isDark.value;
  if (isDark.value) {
    document.documentElement.classList.add("dark");
    localStorage.theme = "dark";
  } else {
    document.documentElement.classList.remove("dark");
    localStorage.theme = "light";
  }
};

// Setup Intersection Observer untuk melacak section aktif (Scrollspy)
const setupScrollSpy = () => {
  const sections = [
    "home",
    "about",
    "skills",
    "experience",
    "projects",
    "contact",
  ];

  const observerOptions = {
    root: null,
    rootMargin: "-20% 0px -70% 0px", // Memicu pergantian saat section masuk di 20% atas layar
    threshold: 0,
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        activeSection.value = entry.target.id;
      }
    });
  }, observerOptions);

  sections.forEach((id) => {
    const el = document.getElementById(id);
    if (el) observer.observe(el);
  });
};

onMounted(() => {
  // Inisialisasi Tema dari LocalStorage atau System Preference
  if (
    localStorage.theme === "dark" ||
    (!("theme" in localStorage) &&
      window.matchMedia("(prefers-color-scheme: dark)").matches)
  ) {
    isDark.value = true;
    document.documentElement.classList.add("dark");
  } else {
    isDark.value = false;
    document.documentElement.classList.remove("dark");
  }

  // Event Listeners
  window.addEventListener("scroll", handleScroll);

  // Tunggu sedikit agar DOM render sempurna sebelum setup ScrollSpy
  setTimeout(() => {
    setupScrollSpy();
  }, 100);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
