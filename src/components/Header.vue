<template lang="pug">
.header
  img.logo(alt="logo", src="../assets/logo.png")
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.header {
  background: linear-gradient(to right, #000, #b3d4fc);
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  .logo {
    padding: 40px;
  }
}
</style>
