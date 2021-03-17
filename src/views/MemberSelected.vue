<template lang="pug">
.memberSelected
  .memberS(v-for="member in user")
    img.profileImageS(:src="member.avatar_url")
    .description
      .name {{ member.name }}
      .otherData Seguidores do GitHub: {{ member.followers }}
      .otherData Repositórios no GitHub: {{ member.public_repos }}
      .otherData Ingressou no GitHub em: {{ member.created_at | formataData }}
    router-link(to="/") Voltar
</template>
<script>
import moment from "moment";
import axios from "axios";
moment.locale("pt-br");
export default {
  data() {
    return {
      user: [],
      login: "",
    };
  },
  created() {
    this.login = this.$route.params.login;
    console.log(this.login);
  },
  mounted() {
    this.getUser();
  },
  methods: {
    async getUser() {
      const response = await axios.get(
        `https://api.github.com/users/${this.login}`
      );
      if (response.status == 200) {
        this.user.push(response.data);
      } else {
        console.log.error("Ocorreu um erro na API");
      }
      // console.log(response);
    },
  },
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
  //   display: flex;
  //   flex-direction: row;
  //   align-items: center;
  //   justify-content: space-around;
  //   position: relative;
  .memberS {
    width: 100%;
    border: 1px solid #b3d4fc;
    border-radius: 5px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    .profileImageS {
      margin: 40px;
      width: 250px;
      border-radius: 5px;
      // position: absolute;
    }
    .description {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
      .name {
        // width: 400px;
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
}
</style>