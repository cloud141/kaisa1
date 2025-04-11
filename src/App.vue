<script setup>
import IoncsAndMore from '@/components/IoncsAndMore.vue';
import Header from '@/components/Header.vue';
</script>

<template>
  <Header />
  <IoncsAndMore name="kaisaR" />

</template>

<style scoped lang="scss">
.body_container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  border: 1px solid red;

  .main_container {
    flex: 1;
    display: flex;
    justify-content: space-around;
    border: 1px solid blue;

    main {
      max-width: min(1280px, calc(100% - 3rem));
      flex: 1;
      border: 1px solid blueviolet;
    }
  }
}
</style>
