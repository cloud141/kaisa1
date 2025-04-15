<script setup>
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
        <IoncsAndMore name="kaisaQ" />
        <p>Q</p>
        <h3>Icathian Rain</h3>
      </div>
      <div class="ability">
        <IoncsAndMore name="kaisaW" />
        <p>W</p>
        <h3>Void Seeker</h3>
      </div>
      <div class="ability">
        <IoncsAndMore name="kaisaE" />
        <p>E</p>
        <h3>Supercharge</h3>
      </div>
      <div class="ability">
        <IoncsAndMore name="kaisaR" />
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

  @media screen and (max-width: 1315px) {
    h2 {
      font-size: 2.5rem;
    }

    p {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 1024px) {
    h2 {
      font-size: 2rem;
    }

    p {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 768px) {
    h2 {
      font-size: 1.5rem;
    }

    p {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 480px) {
    h2 {
      font-size: 1.25rem;
    }

    p {
      font-size: 0.875rem;
    }
  }
}

.abilitiesList {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
  margin-bottom: 3rem;

  @media screen and (max-width: 480px) {
    flex-direction: column;
    align-items: center;
    gap: 2.5rem;
  }

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

  @media screen and (max-width: 1315px) {
    svg {
      max-width: 55px;
    }

  }

  @media screen and (max-width: 1024px) {
    svg {
      max-width: 55px;
    }

    p {
      font-size: 0.8rem;
    }

    h3 {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 768px) {
    svg {
      max-width: 55px;
    }

    p {
      font-size: 0.8rem;
    }

    h3 {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 480px) {
    svg {
      max-width: 55px;
    }

    p {
      font-size: 0.7rem;
    }

    h3 {
      font-size: 0.8rem;
    }
  }
}
</style>
