<script setup>
import SearchIcon from './icons/SearchIcon.vue';
</script>

<template>
    <div>
        <SearchIcon />
        <p>Search for a country...</p>
    </div>
</template>

<style lang="scss" scoped>
    div {
        background-color: var(--color-elements);
        color: var(--color-input);
        padding: 1vw 1.5vw;
        box-shadow: 0 0px 10px 0px rgba(0, 0, 0, 0.1);
        border-radius: 3px;
        display: flex;
        justify-content: start;
        align-items: center;
        p{
            margin-left: 1vw;
        }
        svg {
            fill: var(--color-input);
        }
    }
</style>