<template>
  <navigation />
  <div id="home_container">
    <home />
    <about />
    <works />
    <comments />
    <contact />
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import Home from "./views/Home.vue";

import About from "./views/About.vue";
import Contact from "./views/Contact.vue";
import Works from "./views/Works.vue";
import Comments from "./views/Comments.vue";

export default {
  name: "App",
  components: {
    Navigation,
    Home,
    About,
    Contact,
    Works,
    Comments,
  },
};
</script>

<style  lang="scss">
@import "@/styles/constants.scss";
body {
  margin: 0;
}
#app {
  font-family: Montserrat-Regular, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
}
</style>
