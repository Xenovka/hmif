<template>
  <div class="hero-container">
    <div class="hero-title-container" id="heroTitleContainer"></div>
  </div>
</template>

<script>
// import { gsap } from "gsap";

export default {
  setup() {
    const heroTitleContainer = document.getElementById("heroTitleContainer");
    function heroTitleAnimation() {
      const heroTitle = "HMIF";

      heroTitle.split("").forEach((letter) => {
        const span = document.createElement("span");
        span.classList.add("hero-title");
        span.innerText = letter;

        console.log(heroTitleContainer);
      });
    }

    heroTitleAnimation();
  }
};
</script>

<style lang="scss" scoped>
@import "HeroSection.scss";
</style>
