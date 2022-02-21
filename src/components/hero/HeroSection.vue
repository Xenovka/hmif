<template>
  <div class="hero-container">
    <div class="hero-title-container" id="heroTitleContainer" ref="heroTitle">
      <span class="hero-title-animated">WELCOME</span>
      <span class="hero-title-animated">TO</span>
      <span class="hero-title-animated">HMIF</span>
      <img class="hero-logo" src="../../assets/images/hmif.png" alt="logo hmif" />
    </div>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
import { onMounted } from "@vue/runtime-core";
import { gsap } from "gsap";

export default {
  setup() {
    const heroTitle = ref(null);

    function heroTitleAnimation() {
      const titleElements = document.querySelectorAll(".hero-title-animated");
      const timeline = gsap.timeline({ defaults: { duration: 0.75 } });
      timeline.delay(1);
      titleElements.forEach((el) => {
        timeline.fromTo(
          el,
          { opacity: 0, y: 50 },
          { opacity: 1, y: 0, duration: 0.3, stagger: 0.1, ease: "power2.out" }
        );
      });
      titleElements.forEach((el) => {
        timeline.to(el, { opacity: 0, y: -50, duration: 0.5, stagger: 0.1, delay: 0.25, ease: "power2.out" });
      });
      timeline.to(".hero-logo", { y: "-50%", opacity: 1, duration: 0.5, ease: "power2.out" });
      timeline.to(".hero-logo", { opacity: 0.6, duration: 0.5 });
    }

    onMounted(() => {
      heroTitleAnimation();
    });

    return {
      heroTitle
    };
  }
};
</script>

<style lang="scss" scoped>
@import "HeroSection.scss";
</style>
