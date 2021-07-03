<template>
  <div class="headerAndFooter header">
    <router-link to="/" class="headerBlock headerLeft"
      ><font-awesome-icon :icon="['fas', 'home']"
    /></router-link>

    <div class="headerBlock name">Nikolaus Koopmann</div>
    <div class="headerBlock headerRight">
      <a href="https://www.linkedin.com/in/nikolaus-koopmann-447444107/"
        ><font-awesome-icon :icon="['fab', 'linkedin']"
      /></a>
    </div>
  </div>

  <router-view />

  <div class="headerAndFooter footer">
    <div class="headerBlock headerLeft">
      <a href="mailto:nikolauskoopmann@gmail.com"
        ><font-awesome-icon :icon="['fas', 'envelope']"
      /></a>
    </div>
    <router-link to="cv" class="headerBlock headerRight">cv</router-link>
  </div>
</template>

<style lang="scss">
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

.headerAndFooter {
  position: absolute;
  font-family: MoonGlade, PixoReto, Roboto, Lato, Arial, serif;
  width: 100%;
  display: flex;
  justify-content: space-between;
  font-size: x-large;
  z-index: 1;
}

.header {
  padding-top: 0.5em;
}

.footer {
  padding-bottom: 0.5em;
  bottom: 0;
}

.headerBlock {
  display: inline-block;
}

.headerLeft {
  padding-left: 1em;
}

.headerRight {
  padding-right: 1em;
}

@media all and (max-width: 1000px) {
  .name {
    font-size: large;
  }
}
</style>