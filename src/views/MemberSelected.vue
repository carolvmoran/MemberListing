<template lang="pug">
.memberSelected
  .memberS(v-for="member in user")
    img.profileImageS(:src="member.avatar_url")
    .description
      .name {{ member.name }}
      .otherData Seguidores do GitHub: {{ member.followers }}
      .otherData Repositórios no GitHub: {{ member.public_repos }}
      .otherData Ingressou no GitHub em: {{ member.created_at | formataData }}
  //- Botão de voltar para Home
  router-link.btnBack(to="/") Voltar
</template>
<script>
// Importando moment para alteração de formato de data
import moment from "moment";
// Importando Axios para consumir API
import axios from "axios";
// Adicionando Idioma ao moment
moment.locale("pt-br");
export default {
  data() {
    return {
      // Criando array de usuários que vai receber as informações da API
      user: [],
      // Criando variável para receber o parametro login no metodo created
      login: "",
    };
  },
  // Metodo Created para adicionar rota com parametro login
  created() {
    this.login = this.$route.params.login;
    // console.log(this.login);
  },
  // Metodo mounted para inicializar a função getUser que chama a API
  mounted() {
    this.getUser();
  },
  methods: {
    // Criando metodo para chamar a API de usuário
    async getUser() {
      const response = await axios.get(
        `https://api.github.com/users/${this.login}`
      );
      // 200 é mensagem retornada, (tudo certo para enviar dados ad API)
      if (response.status == 200) {
        this.user.push(response.data);
      } else {
        console.log.error("Ocorreu um erro na API");
      }
      // console.log(response);
    },
  },
  // adicionando função para formatar a data usando moment
  filters: {
    formataData(day) {
      return moment(day).format("lll");
    },
  },
};
</script>
<style lang="scss">
.memberSelected {
  margin: 0 auto;
  margin-top: 40px;
  width: 1080px;
  .memberS {
    width: 100%;
    border: 1px solid #b3d4fc;
    border-radius: 5px;
    margin-bottom: 40px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    .profileImageS {
      margin: 40px;
      width: 250px;
      border-radius: 5px;
    }
    .description {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
      .name {
        font-size: 40px;
        font-weight: 600;
      }
      .otherData {
        margin-top: 20px;
        font-size: 18px;
        margin-left: 20px;
      }
    }
  }
  .btnBack {
    background-color: #b3d4fc;
    border-radius: 5px;
    padding: 10px 20px;
    text-decoration: none;
    color: rgba(0, 0, 0, 0.87);
  }
}
</style>