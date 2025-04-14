<script setup>
import IoncsAndMore from '@/components/IoncsAndMore.vue';
</script>

<template>
    <footer>
        <div class="footerTag">
            <div class="footerRiot">
                <IoncsAndMore name="riotGames" />
                <p>™ & © 2025 - Claudia Olkowski</p>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
.footerTag {
    background-color: $darkPurple;
    margin-top: 300px;

.footerRiot {
  max-width: 1450px;
  margin: 0 auto;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

p {
    @include bodyText;
    color: $yellow;
    margin-top: 10px;
}
}
</style>
