<script setup>
import HeaderVue from '../components/Header.vue';
import CountryCardVue from '../components/CountryCard.vue';
import SearchBoxVue from '../components/SearchBox.vue';
import FilterDropDownVue from '../components/FilterDropDown.vue';
import { useCountriesStore } from '@/stores/countries';

const countriesStore = useCountriesStore()
const { data } = countriesStore
</script>

<template>
  <HeaderVue />
  <main>
    <nav>
      <SearchBoxVue />
      <FilterDropDownVue />
    </nav>
    <section>
      <router-link tag="div" :to="{ name: 'country', params: { country: i.name } }" v-for="i in data">
        <CountryCardVue :name="i.name" :population="i.population" :region="i.region" :capital="i.capital"
          :flag-link="i?.flags.svg || i?.flag" />
      </router-link>
    </section>
  </main>
</template>

<style lang="scss" scoped>
main {
  padding: 4vh 5vw;

  nav {
    margin-bottom: 4vh;
    display: flex;
    justify-content: space-between;
  }

  section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 4vw;
    justify-items: center;
    align-items: center;
  }
}
</style>
