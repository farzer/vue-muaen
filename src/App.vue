<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<style lang="scss">
@import url("~normalize.css/normalize.css");
@import "./assets/scss/custom-reset.scss";
@import "./assets/scss/bootstrap/bootstrap-grid.scss";
@import "./assets/css/font-helper.css";
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Header from "@/components/Header/index.vue";

@Component({
  components: {
    Header
  }
})
export default class App extends Vue {}
</script>
