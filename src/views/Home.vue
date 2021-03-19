<template lang="pug">
.home
  member-listing
</template>

<script>
// Importando Lista de Membros
import MemberListing from "@/components/MemberListing";

export default {
  name: "Home",
  components: {
    MemberListing,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.home {
  margin: 0 auto;
  width: 1080px;
}
</style>
