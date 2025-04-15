<script setup>
import { onMounted, ref } from 'vue';
import { gsap } from 'gsap';

const heroText = ref(null);
const kaisaImage = ref(null);

onMounted(() => {
  gsap.from(heroText.value.querySelectorAll('li'), {
    duration: 2.5,
    opacity: 0,
    y: 100,
    ease: 'power4.out',
    stagger: 0.1
  });

  gsap.from(kaisaImage.value, {
    duration: 2,
    opacity: 0,
    y: 50,
    ease: 'power4.out',
    delay: 0.2
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
        <div class="imgKaisa" ref="kaisaImage">
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

  @media screen and (max-width: 1024px) {
    gap: 1.5rem;
  }

  @media screen and (max-width: 768px) {
    flex-direction: column;
    gap: 1rem;
    max-width: 700px;
  }

  @media screen and (max-width: 480px) {
    max-width: 320px;
  }
}

.heroText {
  @include heading1;
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  white-space: normal;
  max-width: 100%;
  color: $yellow;
  z-index: 1;
  position: relative;
  padding: 0;
  margin: 0;

  span {
    display: inline-block;
  }

  @media screen and (max-width: 1315px) {
    font-size: 17rem;
  }

  @media screen and (max-width: 1024px) {
    font-size: 10rem;
  }

  @media screen and (max-width: 768px) {
    font-size: 7rem;
  }

  @media screen and (max-width: 480px) {
    font-size: 5rem;
  }

}

.imgKaisa {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;

  img {
    width: 650px;
    height: auto;

    @media screen and (max-width: 1315px) {
        width: 500px;
    }

    @media screen and (max-width: 1024px) {
      width: 300px;
    }

    @media screen and (max-width: 768px) {
      width: 230px;
    }

    @media screen and (max-width: 480px) {
      width: 170px;
    }
  }
}
</style>
