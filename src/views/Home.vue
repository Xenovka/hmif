<template>
  <TheNavbar />
  <HeroSection />
</template>

<script>
import TheNavbar from "../components/navbar/TheNavbar.vue";
import HeroSection from "@/components/hero/HeroSection.vue";

export default {
  components: {
    TheNavbar,
    HeroSection
  }
};
</script>
