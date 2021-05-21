<template>
  <v-main>
    <v-container classs="container-default">
      <!-- 1er exo -->
      <Header />
      <!-- 2eme exo : @sidenavToggle est un listener (event) qui permet de savoir s'il doit etre afficher ou non -->
      <!-- en effet, dans le component TheHeader du dossier Navigation il y a un $emit de la sidenavToggle -->
      <!-- displaySidenav à été initialisé à faux, le @sidenavToggle est comme un @click et permet de passé à l'inverse de false ou true selon son état -->
      <HeaderFromNavigation @sidenavToggle="displaySidenav = !displaySidenav" />
      <!-- on passe la propriété show qui est donc bindé car c'est une valeur dynamique et attends true ou false donc de la displaySidenav -->
      <!-- la propriété show à été défini dans le component TheSidenav et attends un boolean -->
      <!-- le @close est dispo lorsque le show est true , il permet de close si le displaySidenav est false-->
      <TheSidenav :show="displaySidenav" @close="displaySidenav = false" />
      <nuxt />
    </v-container>
  </v-main>
</template>

<script>
import Header from "@/components/Header"; // 1er exo
import HeaderFromNavigation from "@/components/Navigation/TheHeader"; //2eme exo
import TheSidenav from "@/components/Navigation/TheSidenav";
export default {
  data() {
    return {
      title: "Vuetify.js",
      displaySidenav: false
    };
  },
  components: { Header, HeaderFromNavigation, TheSidenav }
};
</script>

<style>
html {
  font-family: "Open Sans", sans-serif;
}
body {
  margin: 0;
}
.v-main__wrap {
  flex: 0;
}
.v-main {
  display: block !important;
  flex: 0;
}
</style>
