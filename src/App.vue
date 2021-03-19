<template lang="pug">
#app
  Header
  <router-view />
  Footer
</template>
<script>
// importando Cabeçalho
import Header from "@/components/Header";
// importando Rodapé
import Footer from "@/components/Footer";
export default {
  components: {
    Header,
    Footer,
  },
};
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
