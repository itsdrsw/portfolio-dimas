<template>
  <header
    class="fixed top-0 left-0 w-full z-50 bg-white/80 dark:bg-gray-900/80 backdrop-blur-md border-b border-gray-200 dark:border-gray-800 transition-colors duration-300"
  >
    <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
      <!-- Logo -->
      <a
        href="#"
        class="nav-item text-2xl font-bold text-gray-900 dark:text-white tracking-wide"
      >
        Dimas<span class="text-blue-600 dark:text-blue-500">DS.</span>
      </a>

      <!-- Desktop Menu -->
      <nav class="hidden md:flex space-x-8">
        <a
          v-for="(item, index) in menuItems"
          :key="index"
          :href="`#${item.toLowerCase()}`"
          class="nav-item text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors duration-300 text-sm font-medium"
        >
          {{ item }}
        </a>
      </nav>

      <!-- Aksi Kanan (Desktop & Mobile) -->
      <div class="flex items-center space-x-3 md:space-x-4">
        <!-- Tombol Toggle Dark/Light Mode (Tampil di Desktop & Mobile) -->
        <button
          @click="toggleTheme"
          class="nav-item p-2 rounded-full text-gray-600 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors duration-300 focus:outline-none"
        >
          <!-- Ikon Bulan -->
          <svg
            v-if="!isDark"
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
          <!-- Ikon Matahari -->
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
              d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
            ></path>
          </svg>
        </button>

        <!-- Tombol Hubungi (Hanya Desktop) -->
        <a
          href="#contact"
          class="hidden md:block nav-item px-5 py-2 border border-blue-600 dark:border-blue-500 text-blue-600 dark:text-blue-500 rounded-md hover:bg-blue-600 hover:text-white dark:hover:bg-blue-500 transition-all duration-300 text-sm font-medium"
        >
          Hubungi Saya
        </a>

        <!-- Hamburger Button (Hanya Mobile) -->
        <button
          @click="toggleMobileMenu"
          class="md:hidden nav-item p-2 text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-500 focus:outline-none transition-colors"
        >
          <!-- Ikon Hamburger (Garis Tiga) -->
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
          <!-- Ikon X (Tutup) -->
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

    <!-- Mobile Menu Dropdown (Animasi dengan Vue Transition) -->
    <transition
      enter-active-class="transition duration-300 ease-out transform"
      enter-from-class="-translate-y-4 opacity-0"
      enter-to-class="translate-y-0 opacity-100"
      leave-active-class="transition duration-200 ease-in transform"
      leave-from-class="translate-y-0 opacity-100"
      leave-to-class="-translate-y-4 opacity-0"
    >
      <div
        v-if="isMobileMenuOpen"
        class="md:hidden absolute top-full left-0 w-full bg-white dark:bg-gray-900 border-b border-gray-200 dark:border-gray-800 shadow-xl"
      >
        <nav class="flex flex-col px-6 py-6 space-y-4">
          <a
            v-for="(item, index) in menuItems"
            :key="index"
            :href="`#${item.toLowerCase()}`"
            @click="isMobileMenuOpen = false"
            class="text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 font-semibold text-lg transition-colors"
          >
            {{ item }}
          </a>
          <div class="pt-4 mt-2 border-t border-gray-200 dark:border-gray-800">
            <a
              href="#contact"
              @click="isMobileMenuOpen = false"
              class="block w-full text-center px-5 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-md transition-all duration-300 font-medium"
            >
              Hubungi Saya
            </a>
          </div>
        </nav>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";

const menuItems = ref([
  "Home",
  "About",
  "Skills",
  "Experience",
  "Projects",
  "Contact",
]);
const isDark = ref(false);
const isMobileMenuOpen = ref(false); // State untuk mengatur buka/tutup menu HP

// Fungsi Toggle Menu HP
const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

// Logika untuk Mode Gelap
const toggleTheme = () => {
  isDark.value = !isDark.value;
  if (isDark.value) {
    document.documentElement.classList.add("dark");
    localStorage.setItem("theme", "dark");
  } else {
    document.documentElement.classList.remove("dark");
    localStorage.setItem("theme", "light");
  }
};

onMounted(() => {
  if (
    localStorage.getItem("theme") === "dark" ||
    (!("theme" in localStorage) &&
      window.matchMedia("(prefers-color-scheme: dark)").matches)
  ) {
    isDark.value = true;
    document.documentElement.classList.add("dark");
  }

  gsap.from(".nav-item", {
    y: -30,
    opacity: 0,
    duration: 0.8,
    stagger: 0.1,
    ease: "power3.out",
    delay: 0.2,
  });
});
</script>
