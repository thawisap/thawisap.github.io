<template>
  <v-app>
    <app-tool-bar />
    <home />
    <app-footer />
  </v-app>
</template>

<script>
import AppFooter from "./components/AppFooter.vue";
import AppToolBar from "./components/AppToolBar.vue";
import Home from './view/Home.vue';

export default {
  components: { AppToolBar, AppFooter, Home },
  name: "App",
  data: () => ({
    //
  }),
};
</script>
