<script setup>
import underMidten from '@/components/underMidten.vue';
import IoncsAndMore from './IoncsAndMore.vue';
</script>

<template>
    <div class="abilitiesContainer">
      <!-- Kai'Sa tekst -->
      <div class="headerText">
        <p>Kai'Sa's</p>
        <h2>Abilities</h2>
      </div>
  
      <!-- Abilities ikoner -->
      <div class="abilitiesList">
        <div class="ability">
          <IoncsAndMore name="passiv" />
          <p>Passiv</p>
          <h3>Second Skin</h3>
        </div>
        <div class="ability">
          <IoncsAndMore name="KaisaQ" />
          <p>Q</p>
          <h3>Icathian Rain</h3>
        </div>
        <div class="ability">
          <IoncsAndMore name="KaisaW" />
          <p>W</p>
          <h3>Void Seeker</h3>
        </div>
        <div class="ability">
          <IoncsAndMore name="KaisaE" />
          <p>E</p>
          <h3>Supercharge</h3>
        </div>
        <div class="ability">
          <IoncsAndMore name="KaisaR" />
          <p>R</p>
          <h3>Killer Instinct</h3>
        </div>
      </div>

    </div>

     
  </template>
  

<style scoped lang="scss">
.abilitiesContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; // ← centrering vertikalt
  text-align: center;
  min-height: 65vh; // ← gør sektionen højere
  padding: 4rem 2rem;
  gap: 2rem; // luft mellem header og abilities
}

.headerText {
  p {
    @include bodyText2;
    color: $yellow;
    margin: 0;
  }

  h2 {
    @include heading2;
    color: $white;
    margin-bottom: 2rem;
  }
}

.abilitiesList {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
  margin-bottom: 3rem;
}

.ability {
  display: flex;
  flex-direction: column;
  align-items: center;
 
  text-align: center;
  color: $white;

  p {
    margin: 0.3rem 0 0;
    @include bodyText
  }

  h3 {
    margin: 0;
    @include bodyText2
  }

  svg {
    max-width: 64px;
    height: auto;
    margin-bottom: 15px;
    transition: transform 0.5s ease, border 0.2s ease;

    &:hover {
        transform: scale(1.1);
        box-shadow: 0 0 40px $hoverColor;
        border-radius: 8px;
        cursor: pointer;
    }
  }
}
</style>
