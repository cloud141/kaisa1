<script setup>
import { ref } from 'vue';

const activeModal = ref(null);

const openModal = (name) => {
  activeModal.value = name;
};

const closeModal = () => {
  activeModal.value = null;
};
</script>

<template>

  <div class="abilitiesContainer">
    <div class="headerText">
      <p>who?</p>
      <h2>Discover Kai'sa</h2>
    </div>

    <div class="abilitiesList">
      <!-- FUN -->
      <div class="ability fun" @click="openModal('fun')">
        <div class="gradient-box">
          <div class="imageWrapper funImage">
            <img src="../img/kat2.png" alt="Fun fact kaisa" />
          </div>
          <div class="overlay">
            <h3>Fun facts</h3>
            <p>Kai'sa has family?</p>
          </div>
        </div>
      </div>

      <!-- ROLE -->
      <div class="ability role" @click="openModal('role')">
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
      <div class="ability lore" @click="openModal('lore')">
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
  </div>

  <!-- Modal -->
  <dialog v-if="activeModal" open class="kaisaDialog">
    <div class="modalContent">
      <p v-if="activeModal === 'fun'">Yes – Kassadin is her father 😱</p>
      <p v-else-if="activeModal === 'role'">Kai'Sa is a hybrid marksman and mage.</p>
      <p v-else-if="activeModal === 'lore'">She grew up in the Void after being trapped as a child.</p>

      <button @click="closeModal">Close</button>
    </div>
  </dialog>
</template>
<style scoped lang="scss">
.abilitiesContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; // ← centrering vertikalt
  text-align: center;
  min-height: 20vh; // ← gør sektionen højere
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
  gap: 5rem;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 2rem;
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
    bottom: 2.5rem;
    left: 2.5rem;
    z-index: 3;
    text-align: left;

    h3 {
      @include heading3;
      color: $yellow;
    }

    p {
      margin: 0;
      color: $white;
    }
  }
}

/* Tilpasning pr. billede */
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
  width: 120% !important;
}



.kaisaDialog {
  padding: 2rem;
  background: pink;
  border: none;
  border-radius: 1rem;
  max-width: 400px;
  margin: auto;
  color: $white;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.6);

  .modalContent {
    display: flex;
    flex-direction: column;
    gap: 1rem;

    button {
      align-self: flex-end;
      padding: 0.5rem 1rem;
      background: $purple;
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
  }
}
</style>
