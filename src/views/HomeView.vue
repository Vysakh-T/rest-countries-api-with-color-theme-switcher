<script setup>
import HeaderVue from '../components/Header.vue';
import CountryCardVue from '../components/CountryCard.vue';
import { useCountriesStore } from '@/stores/countries';

const countriesStore = useCountriesStore()
const { data } = countriesStore
</script>

<template>
  <HeaderVue />
  <main>
    <section>
      <CountryCardVue :name="i.name" :population="i.population" :region="i.region" :capital="i.capital" :flag-link="i?.flags.svg || i?.flag"
        v-for="i in data" />
    </section>
  </main>
</template>

<style lang="scss" scoped>
main {
  padding: 4vh 5vw;

  section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 4vw;
    justify-items: center;
    align-items: center;
  }
}
</style>
