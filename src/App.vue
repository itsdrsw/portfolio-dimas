<template>
  <div
    class="bg-gray-50 dark:bg-gray-950 min-h-screen font-sans selection:bg-blue-500 selection:text-white transition-colors duration-300"
  >
    <Navbar />
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ExperienceSection />
    <ProjectsSection />
    <ContactSection />
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import HeroSection from "./components/HeroSection.vue";
import AboutSection from "./components/AboutSection.vue";
import SkillsSection from "./components/SkillsSection.vue";
import ExperienceSection from "./components/ExperienceSection.vue";
import ProjectsSection from "./components/ProjectsSection.vue";
import ContactSection from "./components/ContactSection.vue";
</script>
