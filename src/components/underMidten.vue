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
      <!-- Item 1 -->
      <div class="ability" @click="openModal('fun')">
        <img src="../img/kaisaFun1.png" alt="Fun fact kaisa" />
        <div class="overlay">
          <h3>Fun facts</h3>
          <p>Kai'sa has family?</p>
        </div>
      </div>

      <!-- Item 2 -->
      <div class="ability" @click="openModal('role')">
        <img src="../img/kat1.png" alt="Role kaisa" />
        <div class="overlay">
          <h3>Role</h3>
          <p>Marksman / Mage</p>
        </div>
      </div>

      <!-- Item 3 -->
      <div class="ability" @click="openModal('lore')">
        <img src="../img/kaisaLore.png" alt="Lore kaisa" />
        <div class="overlay">
          <h3>Lore</h3>
          <p>Where is she from?</p>
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
  </div>
</template>

<style scoped lang="scss">

.abilitiesContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; // ← centrering vertikalt
  text-align: center;
  min-height: 55vh; // ← gør sektionen højere
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
  justify-content: space-between;
  width: 100%;
  gap: 1rem;
  flex-wrap: nowrap;

  @media (max-width: 1024px) {
    flex-wrap: wrap;
  }
}

.ability {
  position: relative;
  flex: 1 1 0%;
  max-width: 600px; // eller den bredde du ønsker
  height: 400px; 
  cursor: pointer;
  overflow: hidden;
  display: flex;
  flex-shrink: 0; // forhindrer flex i at squish'e dem

  img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
    transition: transform 0.5s ease, border 0.2s ease;

    &:hover {
        transform: scale(1.1);
        box-shadow: 0 0 40px $hoverColor;
        border-radius: 8px;
        cursor: pointer;
    }
}

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
    color: $white;
    background: none; // ← fjernet mørk baggrund

    h3,
    p {
      margin: 0;
      text-shadow: 0 0 5px rgba(0, 0, 0, 0.7); // gør teksten læsbar uden mørk baggrund
    }
  }
}


.kaisaDialog {
  padding: 2rem;
  background: pink;
  border: none;
  border-radius: 1rem;
  max-width: 400px;
  margin: auto;
  color: $white;
  box-shadow: 0 0 20px rgba(0,0,0,0.6);

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
