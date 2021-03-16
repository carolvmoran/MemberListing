<template lang="pug">
.memberSelected
  .memberS(v-for="item in user")
    img.profileImageS(:src="item.avatar_url")
    .description
      .name {{ item.name }}
      .otherData Seguidores do GitHub: {{ item.followers }}
      .otherData Repositórios no GitHub: {{ item.public_repos }}
      .otherData Ingressou no GitHub em: {{ item.created_at | formataData }}
    router-link(to="/") Voltar
</template>
<script>
import moment from "moment";
moment.locale("pt-br");
export default {
  data() {
    return {
      user: [
        {
          login: "Acquati",
          id: 15040050,
          node_id: "MDQ6VXNlcjE1MDQwMDUw",
          avatar_url: "https://avatars.githubusercontent.com/u/15040050?v=4",
          gravatar_id: "",
          url: "https://api.github.com/users/Acquati",
          html_url: "https://github.com/Acquati",
          followers_url: "https://api.github.com/users/Acquati/followers",
          following_url:
            "https://api.github.com/users/Acquati/following{/other_user}",
          gists_url: "https://api.github.com/users/Acquati/gists{/gist_id}",
          starred_url:
            "https://api.github.com/users/Acquati/starred{/owner}{/repo}",
          subscriptions_url:
            "https://api.github.com/users/Acquati/subscriptions",
          organizations_url: "https://api.github.com/users/Acquati/orgs",
          repos_url: "https://api.github.com/users/Acquati/repos",
          events_url: "https://api.github.com/users/Acquati/events{/privacy}",
          received_events_url:
            "https://api.github.com/users/Acquati/received_events",
          type: "User",
          site_admin: false,
          name: "Leandro Acquati",
          company: null,
          blog: "https://acquati.github.io/curriculo.github.io/",
          location: "Bauru, SP",
          email: null,
          hireable: true,
          bio: "Full Stack Developer.",
          twitter_username: null,
          public_repos: 31,
          public_gists: 2,
          followers: 5,
          following: 9,
          created_at: "2015-10-08T21:21:18Z",
          updated_at: "2021-03-11T10:54:36Z",
        },
      ],
    };
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