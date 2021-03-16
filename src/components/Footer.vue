<template lang="pug">
.footer
  h3.nameGroup ___ Tesseract
  .socialMedia
    .icons
      a(href="https://www.instagram.com/grupotesseract/", target="_blank")
        i.fab.fa-instagram
      a(href="https://www.facebook.com/grupotesseract", target="_blank")
        i.fab.fa-facebook-square
      a(href="https://github.com/grupotesseract", target="_blank")
        i.fab.fa-github
      a(href="https://medium.com/grupo-tesseract", target="_blank")
        i.fab.fa-medium
      a(
        href="https://www.linkedin.com/company/grupotesseract/about/",
        target="_blank"
      )
        i.fab.fa-linkedin
      a(href="", target="_blank")
        i.fab.fa-whatsapp
</template>
<script>
export default {};
</script>
<style lang="scss">
.footer {
  background: linear-gradient(to right, #000, #b3d4fc);
  margin-top: 40px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-direction: column;
  width: 100%;
  //   height: 100px;
  color: white;
  .nameGroup {
    margin: 50px 0;
    text-align: left;
    font-size: 35px;
    width: 90%;
  }
  .socialMedia {
    // text-align: left;
    font-size: 32px;
    width: 90%;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    .icons {
      font-size: 40;
      margin-bottom: 50px;
      a {
        color: white;
        text-decoration: none;
        i {
          margin-right: 40px;
        }
      }
    }
  }
}
</style>