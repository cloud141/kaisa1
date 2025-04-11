<script setup>
import IoncsAndMore from './IoncsAndMore.vue';
</script>

<template>
    <div class="search-wrapper">
        <input type="text" placeholder="Søg" class="search-input" />
        <IoncsAndMore name="search" />
    </div>
</template>

<style scoped lang="scss">
.search-wrapper, input {
    display: flex;
    align-items: center;
    border: 1px solid black;
    border-radius: 2rem;
    padding: 0.5rem 1rem;
    background-color: pink;

    .search-input {
        border: none;
        outline: none;
        font-style: italic;
        flex: 1;
    }
}
</style>
