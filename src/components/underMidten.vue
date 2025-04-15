<script setup>
import { ref } from 'vue'

const modalType = ref(null)

const modalData = {
  role: {
    subtitle: "Kai’sa",
    title: "Role",
    text: `Kaisa is really strong right now into a lot of things. You would think her lack of mobility would hinder her, but her E really helps reposition after the upgrade. That combined with Galeforce and her ultimate she is quite mobile.`,
    image: new URL('@/img/modal2.jpg', import.meta.url).href
  },
  lore: {
    subtitle: "Kai’sa",
    title: "Lore",
    text: `Once lost in the Void, Kai’Sa survived through sheer willpower and adapted to become one with a living Void-suit. Now, she fights between two worlds – the Void and humanity.`,
    image: new URL('@/img/modal3.jpg', import.meta.url).href
  },
  fun: {
    subtitle: "Kai’sa",
    title: "Fun Fact",
    text: `Did you know Kai’Sa’s symbiote suit is partially alive and bonded to her body? That’s what gives her all those cool powers.`,
    image: new URL('@/img/modal1.jpg', import.meta.url).href
  }
}
</script>

<template>
  <div class="abilitiesContainer">
    <div class="headerText">
      <p>who?</p>
      <h2>Discover Kai'sa</h2>
    </div>

    <div class="abilitiesList">
      <!-- FUN -->
      <div class="ability fun" @click="modalType = 'fun'">
        <div class="gradient-box">
          <div class="imageWrapper funImage">
            <img src="../img/kat2.png" alt="Fun fact kaisa" />
          </div>
          <div class="overlay">
            <h3>Fun facts</h3>
            <p>Did you know?</p>
          </div>
        </div>
      </div>

      <!-- ROLE -->
      <div class="ability role" @click="modalType = 'role'">
        <div class="gradient-box">
          <div class="imageWrapper roleImage">
            <img src="../img/kat.png" alt="Role kaisa" />
          </div>
          <div class="overlay">
            <h3>Role</h3>
            <p>Marksman / Mage</p>
          </div>
        </div>
      </div>

      <!-- LORE -->
      <div class="ability lore" @click="modalType = 'lore'">
        <div class="gradient-box">
          <div class="imageWrapper loreImage">
            <img src="../img/kat3.png" alt="Lore kaisa" />
          </div>
          <div class="overlay">
            <h3>Lore</h3>
            <p>Where is she from?</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <transition name="fade">
      <div v-if="modalType" class="modalOverlay" @click.self="modalType = null">
        <div class="modalContent">
          <div class="imageContainer">
            <img :src="modalData[modalType].image" alt="Kai'sa" />
            <div class="gradientOverlay"></div>
          </div>
          <div class="textContent">
            <p class="subtitle">{{ modalData[modalType].subtitle }}</p>
            <h2>{{ modalData[modalType].title }}</h2>
            <p class="description">{{ modalData[modalType].text }}</p>
          </div>
        </div>
      </div>
    </transition>

  </div>
</template>

<style scoped lang="scss">
.abilitiesContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 4rem 2rem;
  gap: 2rem;
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
  gap: 5.7rem;
  justify-content: center;
  flex-wrap: wrap;
}

.ability {
  width: 400px;
  height: 380px;
  position: relative;
  cursor: pointer;

  .gradient-box {
    background: linear-gradient(to bottom, $purple, $black);
    border-radius: 2.5rem;
    width: 100%;
    height: 100%;
    overflow: hidden;
    padding-top: 60px;
    transition: box-shadow 0.3s ease;

    &:hover {
      box-shadow: 0 0 40px 10px $hoverColor;
    }
  }

  .imageWrapper {
    position: absolute;
    left: 0;
    width: 100%;
    height: auto;
    z-index: 2;

    img {
      width: 100%;
      height: auto;
      object-fit: contain;
      pointer-events: none;
    }

  }

  .overlay {
    position: absolute;
    bottom: 2rem;
    left: 2.5rem;
    z-index: 3;
    text-align: left;

    h3 {
      color: $yellow;
      @include heading3;
    }

    p {
      color: $white;
      @include bodyText;
    }
  }
}

.funImage {
  top: 1px !important;
  width: 110% !important;
}

.roleImage {
  top: -24px !important;
  width: 100% !important;
}

.loreImage {
  top: 1px !important;
  width: 119% !important;
}

// Modal styling
.modalOverlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  backdrop-filter: blur(10px);
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modalContent {
  background: linear-gradient(to top, $darkPurple 0%, $linarColor 10%);
  border: 3px solid $hoverColor;
  border-radius: 3.125rem;
  width: 90%;
  max-width: 650px;
  overflow: hidden;
  position: relative;
  animation: fadeInUp 0.4s ease-out;
  box-shadow: 0 0 30px $hoverColor;
}

.imageContainer {
  position: relative;

  img {
    width: 100%;
    height: auto;
    object-fit: cover;
  }

  .gradientOverlay {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 40%;
    background: linear-gradient(to top, $linarColor 10%, transparent 100%);
  }
}

.textContent {
  padding: 2rem 4rem 4rem;
  text-align: left;

  .subtitle {
    @include bodyText2;
    color: $yellow;
    margin-bottom: -5px;
  }

  h2 {
    @include heading2;
    color: $white;
    margin-bottom: 1px;
  }

  .description {
    color: $white;
    line-height: 1.6;
  }
}



// Animation
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media screen and (max-width: 700px) {
  .abilitiesList {
    gap: 2rem;
  }

  .funImage img {
    width: 107.6% !important;
  }

  .roleImage img {
    width: 92% !important;
  }

  .loreImage img {
    width: 117% !important;
  }

  .ability {
    width: 280px;
    height: 260px;

    .gradient-box {
      padding-top: 40px;
      border-radius: 2rem;
    }

    .overlay {
      bottom: 1.5rem;
      left: 1.5rem;

      h3 {
        font-size: 1.25rem;
      }

      p {
        font-size: 0.875rem;
      }
    }

    .imageWrapper {
      img {
        width: 100%;
        object-fit: contain;
      }
    }
  }

  .funImage,
  .roleImage,
  .loreImage {
    width: 100% !important;
    top: 0 !important;
  }
}

@media screen and (max-width: 480px) {

  .funImage img {
    width: 82% !important;
  }

  .roleImage img {
    width: 70% !important;
  }

  .loreImage img {
    width: 89% !important;
  }
  .ability {
    width: 90vw;
    height: 240px;
  }

  .overlay {
    h3 {
      font-size: 1rem;
    }

    p {
      font-size: 0.75rem;
    }
  }
}
</style>
