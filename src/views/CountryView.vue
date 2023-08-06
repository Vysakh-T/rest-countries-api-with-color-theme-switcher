<script setup>
const props = defineProps({
    country: String,
})
</script>

<template>
  <HeaderVue />
  <main>
    <nav>
      <SearchBoxVue />
      <FilterDropDownVue />
    </nav>
    <section>
      <h1>Hello {{  $route.params.country }}</h1>
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
