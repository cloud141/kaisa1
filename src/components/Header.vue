<!-- Header.vue -->
<script setup>
import IoncsAndMore from '@/components/IoncsAndMore.vue';
import Hero from '@/components/Hero.vue';
</script>

<template>
  <div class="heroSection">
    <div class="overlayContent">
      <div class="mainContainer">
        <div class="container">
          <IoncsAndMore name="lolLogo" />

          <div class="center">
            <div class="searchWrapper">
              <IoncsAndMore name="search" class="search-icon" />
              <input type="text" placeholder="Search..." class="searchInput" />
            </div>
          </div>

          <div class="icons">
            <IoncsAndMore name="nofi" />
            <IoncsAndMore name="settings" />
          </div>
        </div>
        <Hero />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.heroSection {
  width: 100%;
  min-height: 800px;
  background-image: url('@/assets/img/bg1.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;

  .overlayContent {
    position: relative;
    z-index: 1;
    padding: 2rem;
  }
}

.mainContainer {
  max-width: 1450px;
  margin: 0 auto;
  
  display: flex;
  flex-direction: column;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

.center {
  flex: 1;
  display: flex;
  justify-content: center;
}

.searchWrapper {
  display: flex;
  align-items: center;
  border: 3px solid $purple;
  border-radius: 2rem;
  padding: 0.5rem 1.5rem;
  background: none;
  max-width: 400px;
  width: 100%;
}

.searchInput {
  border: none;
  outline: none;
  @include bodyText;
  flex: 1;
  background: none;
  color: $white;
  padding-left: 0.5rem;
}

.search-icon {
  transition: transform 0.3s ease;
  cursor: pointer;

  &:hover {
    transform: scale(1.2);
  }
}

.icons {
  display: flex;
  gap: 10px;
}
</style>
