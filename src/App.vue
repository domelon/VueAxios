<template>
  <h2>VueAxios</h2>
  <ul>
    <li v-for="country in info" :key="country.id">
      {{ country.name }} | {{ country.capital }} | {{ country.area }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      info: [],
    };
  },
  async mounted() {
    const { data } = await this.axios.get(
      "https://flask.wiejskomiejskie.pl/countries"
    );
    this.info = data;
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
</style>

