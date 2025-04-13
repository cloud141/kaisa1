<script setup>
import IoncsAndMore from '@/components/IoncsAndMore.vue';
import Header from '@/components/Header.vue';
import Header1 from '@/components/Header1.vue';
</script>

<template>

<div class="bodyContainer">
    <div class="mainContainer">
      <main>
        <Header />
        <Header1 />

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
    }
  }
}
</style>
