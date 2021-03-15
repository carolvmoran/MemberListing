<template lang="pug">
.home
  Header
  member-listing
</template>

<script>
import Header from "@/components/Header";
import MemberListing from "@/components/MemberListing";

export default {
  name: "Home",
  components: {
    Header,
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
</style>
