<template lang="pug">
.memberListing
  //- Adicionando Campo de Busca
  .searchContainer
    img.searchImage(src="@/assets/search.svg", alt="alt")
    input.search(v-model="filtro", type="text", placeholder="Buscar Membro")
  //- Lista de Membros
  .member 
    .listMember(
      v-for="item in memberFilter",
      @click="() => { $router.push(`/memberSelected/${item.login}`).catch(() => {}); }"
    )
      img.profileImage(:src="item.avatar_url")
      .login {{ item.login }}
    //- Adicionando V-if para o caso de a busca não ser encontrada
    .listMember(v-if="!memberFilter.length")
      .notFound Nenhum resultado encontrado para esta busca.
</template>
<script>
// Criando a constante axios
const axios = require("axios");
export default {
  data() {
    return {
      // Criando Variável para filtro de busca
      filtro: "",
      // Criando array de objetos para receber dados da API de Membros
      dados: [],
    };
  },
  // Metodo mounted para inicializar a função getData que chama a API
  mounted() {
    this.getData();
  },
  methods: {
    // Criando metodo para chamar a API de membros
    async getData() {
      const response = await axios.get(
        "https://api.github.com/orgs/grupotesseract/public_members"
      );
      // 200 é mensagem retornada, (tudo certo para enviar dados ad API)
      if (response.status == 200) {
        this.dados = response.data;
      } else {
        console.log.error("Ocorreu um erro na API");
      }
    },
  },
  computed: {
    // Criando função para filtro de Busca
    memberFilter() {
      if (this.filtro) {
        let exp = new RegExp(this.filtro.trim(), "i");
        return this.dados.filter((nickName) => exp.test(nickName.login));
      } else {
        return this.dados;
      }
    },
  },
};
</script>
<style lang="scss">
.memberListing {
  width: 100%;
  height: 100%;
  .searchContainer {
    width: 100%;
    position: relative;
    margin-top: 40px;
    .searchImage {
      position: absolute;
      width: 36px;
      left: 20px;
      top: 50%;
      transform: translateY(-50%);
    }
    .search {
      outline: none;
      border-radius: 50px;
      width: 100%;
      height: 50px;
      border: 1px solid #b3d4fc;
      padding-left: 60px;
      padding-right: 20px;
      font-size: 18px;
      &::placeholder {
        color: rgba($color: #808285, $alpha: 0.5);
      }
    }
  }
  .member {
    display: flex;
    align-items: center;
    justify-content: space-around;
    flex-direction: column;
    margin-top: 40px;
    .listMember {
      width: 100%;
      border: 1px solid #b3d4fc;
      border-radius: 5px;
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      cursor: pointer;
      .profileImage {
        width: 100px;
        padding: 20px;
        border-radius: 50%;
      }
      .login {
        width: 100px;
        padding: 20px;
      }
      .notFound {
        padding: 100px 0;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        font-size: 18px;
      }
    }
  }
}
</style>