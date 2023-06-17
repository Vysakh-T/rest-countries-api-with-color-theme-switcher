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
        <img :src="flagLink" :alt="'Flag of ' + props.name" />
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
    background: white;
    width: 100%;
    box-shadow: 0 0px 10px 0px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    overflow: hidden;

    img {
        width: 100%;
        object-fit: cover;
        height: 23vh;
    }

    .details {
        padding-block: 1vw 2.5vw;
        padding-inline: 2vw;
        width: 100%;

        h4 {
            padding-bottom: 0.5vw;
            font-weight: 800;
            font-size: 16px;
        }

        p {
            b {
                font-weight: 600;
            }
        }
    }
}
</style>