<script setup>
import { onMounted, ref } from 'vue';
import { gsap } from 'gsap';

const heroText = ref(null);

onMounted(() => {
  gsap.from(heroText.value.querySelectorAll('li'), {
    duration: 2.5,
    opacity: 0,
    y: 100,
    ease: 'power4.out',
    stagger: 0.1
  });
});
</script>

<template>
    <div class="heroKaisaContainer">
      <div class="overlayWrapper">
        <ul class="heroText" ref="heroText">
          <li><span>Kai</span></li>
          <li><span>&nbsp;</span></li>
          <li><span>sa</span></li>
        </ul>
        <div class="imgKaisa">
          <img src="@/img/kaisa1.png" alt="Kaisa" />
        </div>
      </div>
    </div>
  </template>
  

<style scoped lang="scss">
.heroKaisaContainer {
  display: flex;
  justify-content: center;
  align-items: center;

}

.overlayWrapper {
  position: relative;
  width: 100%;
  max-width: 1200px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.heroText {
  @include heading1;
  list-style: none;
  display: flex;
  color: $yellow;
  z-index: 1;
  position: relative;

  span {
    display: inline-block;
  }
}

.imgKaisa {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;

  img {
    width: 800px; // Juster efter behov
    height: auto;
  }
}

</style>
