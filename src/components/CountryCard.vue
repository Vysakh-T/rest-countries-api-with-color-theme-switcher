<script setup>
// Add validation
const props = defineProps({
    name: String,
    population: Number,
    region: String,
    capital: String,
    flagLink: String,
})
const numLocale = 'en-US'
</script>

<template>
    <div class="card">
        <img :src="flagLink" :alt="'Flag of ' + props.name" draggable="false"/>
        <div class="details">
            <h4>
                {{ props.name }}
            </h4>
            <p><b>Population:</b> {{ props.population.toLocaleString(numLocale) }}</p>
            <p><b>Region:</b> {{ props.region }}</p>
            <p><b>Capital:</b> {{ props.capital }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    background: var(--color-elements);
    width: 100%;
    box-shadow: 0 0px 10px 0px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    overflow: hidden;

    img {
        width: 100%;
        object-fit: cover;
        aspect-ratio: 1.5;

        //Image non-selectable
        user-select: none;
        -moz-user-select: none;
        -webkit-user-select: none;
        -ms-user-select: none;
    }

    //Make h4 bigger and deal with overflow
    .details {
        padding-block: 1vw 2vw;
        padding-inline: 1.5vw;
        width: 100%;

        h4 {
            padding-bottom: 0.5vw;
            font-weight: 800;
            font-size: 14px;
        }

        p {
            b {
                font-weight: 600;
            }
        }
    }
}
</style>