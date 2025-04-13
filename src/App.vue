<script setup>
import IoncsAndMore from '@/components/IoncsAndMore.vue';
import underMidten from '@/components/underMidten.vue';
import Header from '@/components/Header.vue';
import Midten from '@/components/Midten.vue';
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
  </div>

</template>

<style scoped lang="scss">
.bodyContainer {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  border: 1px solid red;
  background: $veryDarkPurple;

  .mainContainer {
    flex: 1;
    display: flex;
    justify-content: space-around;
    border: 1px solid blue;

    main {
      max-width: min(1450px, calc(100% - 3rem));
      flex: 1;
      border: 1px solid blueviolet;
      width: 100%;
      background-image: url('@/img/storKaisa.png');
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      position: relative;
    }
  }
}
</style>
