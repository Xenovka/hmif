<template>
  <div class="nav">
    <ul class="nav__item-container">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
      <li><a href="#">Events</a></li>
    </ul>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { onMounted } from "@vue/runtime-core";

export default {
  setup() {
    function gsapAnimation() {
      const navItems = document.querySelectorAll(".nav__item-container li");
      const timeline = gsap.timeline({ defaults: { duration: 0.75 } });

      timeline.delay(1);
      navItems.forEach((item) => {
        timeline.fromTo(
          item,
          { y: -100, opacity: 0 },
          { y: 0, opacity: 1, duration: 0.75, stagger: 0.5, ease: "elastic.out(0.75, 0.5)" },
          "<50%"
        );
      });
    }

    onMounted(() => {
      gsapAnimation();
    });

    return {};
  }
};
</script>

<style lang="scss" scoped>
@import "TheNavbar.scss";
</style>
