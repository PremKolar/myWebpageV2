<template>
  <div
    class="headerAndFooter header"
    :class="{ headerAndFooterYmargined: page === 'Home' }"
  >
    <div class="headerBlock headerLeft btn" @click="page = 'Home'">
      <font-awesome-icon size="lg" :icon="['fas', 'home']" />
    </div>

    <div class="headerBlock headerRight">
      <a href="https://www.linkedin.com/in/nikolaus-koopmann-447444107/"
        ><font-awesome-icon :icon="['fab', 'linkedin']"
      /></a>
    </div>
  </div>
  <CV v-if="page === 'CV'"></CV>
  <Home v-else-if="page === 'Home'"></Home>
  <div
    class="headerAndFooter footer"
    :class="{ headerAndFooterYmargined: page === 'Home' }"
  >
    <div class="headerBlock headerLeft">
      <a href="mailto:nikolauskoopmann@gmail.com"
        ><font-awesome-icon :icon="['fas', 'envelope']"
      /></a>
    </div>
    <div v-show="page === 'Home'" class="headerBlock name">
      Nikolaus Koopmann
    </div>
    <div class="headerBlock headerRight btn headerFont" @click="page = 'CV'">
      cv
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CV from "@/views/CV.vue";
import Home from "@/views/Home.vue";

@Options({
  components: {
    CV,
    Home,
  },
})
export default class App extends Vue {
  private page: "Home" | "CV" = "Home";
}
</script>

<style lang="scss">
:root {
  --maxwidth: 1600px;
  --maxwidthHalf: 800px;
  --maxheight: 1066px;
}

body {
  margin: 0;
  //padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: azure;
  background-color: black;
  margin: auto;
  //min-height: 98vh;
}

a {
  font-weight: bold;
  color: beige;
  text-decoration: none;
  &.router-link-exact-active {
    color: antiquewhite;
  }
}

.btn {
  cursor: pointer;
}

.headerAndFooter {
  position: fixed;
  font-family: Hendrickson, PalmSprings, MoonGlade, PixoReto, Roboto, Lato,
    Arial, serif;
  width: 100%;
  display: flex;
  justify-content: space-between;
  font-size: x-large;
  z-index: 1;
  max-width: var(--maxwidth);
  margin-left: max(0px, calc(50vw - var(--maxwidthHalf)));
  margin-right: max(0px, calc(50vw - var(--maxwidthHalf)));
}

.headerAndFooterYmargined {
  margin-top: max(0px, calc((100vh - var(--maxheight)) / 2));
  margin-bottom: max(0px, calc((100vh - var(--maxheight)) / 2));
}

.header {
  padding-top: 0.5em;
}

.footer {
  padding-bottom: 0.5em;
  bottom: 0;
}

.headerBlock {
  display: flex;
  flex-direction: column-reverse;
}

.headerLeft {
  padding-left: 1em;
}

.headerRight {
  padding-right: 1em;
}

.headerFont {
  font-family: MoonGlade, PalmSprings, MoonGlade, PixoReto, Roboto, Lato, Arial,
    serif;
  padding-bottom: 9px;
}

.name {
  font-size: 4em;
}

@media all and (max-width: 1000px) {
  .name {
    font-size: 2em;
  }
}

@font-face {
  font-family: "PixoReto";
  src: local("PixoReto"),
    url(./assets/fonts/PixoReto/PixoRetoSP-Regular.ttf) format("truetype");
}

@font-face {
  font-family: "PixoRetoAlt";
  src: local("PixoRetoAlt"),
    url("./assets/fonts/PixoRetoAlt/Pixo Reto.ttf") format("truetype");
}

@font-face {
  font-family: "MoonGlade";
  src: local("MoonGlade"),
    url("./assets/fonts/Moonglade/MoongladeDemoBold-jOzM.ttf")
      format("truetype");
}

@font-face {
  font-family: Montserrat;
  src: local("Montserrat"), url("./assets/fonts/Montserrat-Regular.ttf");
}

@font-face {
  font-family: PalmSprings;
  src: local("PalmSprings"),
    url("assets/fonts/PalmspringsPersonalUseRegular-ALqyA.ttf");
}

@font-face {
  font-family: Hendrickson;
  src: local("Hendrickson"), url("assets/fonts/hendrick/Hendrickson-K7GOD.otf");
}
</style>
