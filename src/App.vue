<template lang="pug">
#app
  Header
  <router-view />
</template>
<script>
import Header from "@/components/Header";
export default {
  components: {
    Header,
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

// #nav {
//   padding: 30px;
//   font-family: "Black Ops One", cursive;

//   a {
//     font-weight: bold;
//     color: #2c3e50;
//   }
// }
</style>
