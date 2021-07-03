<template>
  <!--  <div id="nav">-->
  <!--    <router-link to="/">Home</router-link>-->
  <!--    |-->
  <!--    <router-link to="/about">About</router-link>-->
  <!--  </div>-->
  <router-view />
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

</style>
