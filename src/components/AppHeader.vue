<template>
  <header>
    <div class="container-header">
      <div class="text">
        <h2>BOOTFLIX</h2>
      </div>
      <div>
        <input type="text" placeholder="Scrivi" v-model="filmsSearch" />
        <button @click="$emit('searchClick', filmsSearch)">Cerca</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      filmsSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: chartreuse;

  .container-header {
    height: 10vh;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
