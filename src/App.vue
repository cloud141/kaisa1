<script setup>
import underMidten from '@/components/underMidten.vue';
import Header from '@/components/Header.vue';
import Midten from '@/components/Midten.vue';
import Footer from '@/components/Footer.vue';
</script>

<template>
  <div class="bodyContainer">
    <Header />
    <div class="mainContainer">
      <main>
        <Midten />
        <underMidten />
      </main>
    </div>
    <Footer />
  </div>

</template>

<style scoped lang="scss">
body {
  overflow-x: hidden;
}
.bodyContainer {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: $veryDarkPurple;
  background-image: url('@/img/storKaisa.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;

  .mainContainer {
    flex: 1;
    display: flex;
    justify-content: space-around;

    main {
      max-width: min(1450px, calc(100% - 3rem));
      flex: 1;
      width: 100%;
    }
  }
}
</style>
