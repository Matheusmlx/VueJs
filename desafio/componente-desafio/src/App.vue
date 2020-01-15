<template>
  <v-app>
    <menu-lateral />
    <toolbar />
    <v-content>
      <galeria-fotos />
    </v-content>
    <footer-home />
  </v-app>
</template>

<script>
import Footer from "./components/footer";
import GaleriaFotos from "./components/galeriaFotos";
import menuLateral from "./components/menuLateral.vue";
import toolbar from "./components/toolbar";
export default {
  components: {
    "menu-lateral": menuLateral,
    toolbar,
    "galeria-fotos": GaleriaFotos,
    "footer-home": Footer
  }
};
</script>
