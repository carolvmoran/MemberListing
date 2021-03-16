<template lang="pug">
.memberListing
  .searchContainer
    img.searchImage(src="@/assets/search.svg", alt="alt")
    input.search(v-model="filtro", type="text", placeholder="Buscar Membro")
  .member 
    .listMember(
      v-for="item in memberFilter",
      @click="() => { $router.push(`/memberSelected/${item.login}`).catch(() => {}); }"
    )
      img.profileImage(:src="item.avatar_url")
      .login {{ item.login }}
    .listMember(v-if="!memberFilter.length")
      .notFound Nenhum resultado encontrado para esta busca.
      //- .repositories 13
      //- .followers 1
      //- .date 6/12/2020
</template>
<script>
export default {
  data() {
    return {
      filtro: "",
      dados: [
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
        },
        {
          login: "wesleyhf",
          id: 2936121,
          node_id: "MDQ6VXNlcjI5MzYxMjE=",
          avatar_url: "https://avatars.githubusercontent.com/u/2936121?v=4",
          gravatar_id: "",
          url: "https://api.github.com/users/wesleyhf",
          html_url: "https://github.com/wesleyhf",
          followers_url: "https://api.github.com/users/wesleyhf/followers",
          following_url:
            "https://api.github.com/users/wesleyhf/following{/other_user}",
          gists_url: "https://api.github.com/users/wesleyhf/gists{/gist_id}",
          starred_url:
            "https://api.github.com/users/wesleyhf/starred{/owner}{/repo}",
          subscriptions_url:
            "https://api.github.com/users/wesleyhf/subscriptions",
          organizations_url: "https://api.github.com/users/wesleyhf/orgs",
          repos_url: "https://api.github.com/users/wesleyhf/repos",
          events_url: "https://api.github.com/users/wesleyhf/events{/privacy}",
          received_events_url:
            "https://api.github.com/users/wesleyhf/received_events",
          type: "User",
          site_admin: false,
        },
        {
          login: "evandrododo",
          id: 192278,
          node_id: "MDQ6VXNlcjE5MjI3OA==",
          avatar_url: "https://avatars.githubusercontent.com/u/192278?v=4",
          gravatar_id: "",
          url: "https://api.github.com/users/evandrododo",
          html_url: "https://github.com/evandrododo",
          followers_url: "https://api.github.com/users/evandrododo/followers",
          following_url:
            "https://api.github.com/users/evandrododo/following{/other_user}",
          gists_url: "https://api.github.com/users/evandrododo/gists{/gist_id}",
          starred_url:
            "https://api.github.com/users/evandrododo/starred{/owner}{/repo}",
          subscriptions_url:
            "https://api.github.com/users/evandrododo/subscriptions",
          organizations_url: "https://api.github.com/users/evandrododo/orgs",
          repos_url: "https://api.github.com/users/evandrododo/repos",
          events_url:
            "https://api.github.com/users/evandrododo/events{/privacy}",
          received_events_url:
            "https://api.github.com/users/evandrododo/received_events",
          type: "User",
          site_admin: false,
        },
        {
          login: "ltgouvea",
          id: 12522078,
          node_id: "MDQ6VXNlcjEyNTIyMDc4",
          avatar_url: "https://avatars.githubusercontent.com/u/12522078?v=4",
          gravatar_id: "",
          url: "https://api.github.com/users/ltgouvea",
          html_url: "https://github.com/ltgouvea",
          followers_url: "https://api.github.com/users/ltgouvea/followers",
          following_url:
            "https://api.github.com/users/ltgouvea/following{/other_user}",
          gists_url: "https://api.github.com/users/ltgouvea/gists{/gist_id}",
          starred_url:
            "https://api.github.com/users/ltgouvea/starred{/owner}{/repo}",
          subscriptions_url:
            "https://api.github.com/users/ltgouvea/subscriptions",
          organizations_url: "https://api.github.com/users/ltgouvea/orgs",
          repos_url: "https://api.github.com/users/ltgouvea/repos",
          events_url: "https://api.github.com/users/ltgouvea/events{/privacy}",
          received_events_url:
            "https://api.github.com/users/ltgouvea/received_events",
          type: "User",
          site_admin: false,
        },
        {
          login: "gugarosa",
          id: 4120639,
          node_id: "MDQ6VXNlcjQxMjA2Mzk=",
          avatar_url: "https://avatars.githubusercontent.com/u/4120639?v=4",
          gravatar_id: "",
          url: "https://api.github.com/users/gugarosa",
          html_url: "https://github.com/gugarosa",
          followers_url: "https://api.github.com/users/gugarosa/followers",
          following_url:
            "https://api.github.com/users/gugarosa/following{/other_user}",
          gists_url: "https://api.github.com/users/gugarosa/gists{/gist_id}",
          starred_url:
            "https://api.github.com/users/gugarosa/starred{/owner}{/repo}",
          subscriptions_url:
            "https://api.github.com/users/gugarosa/subscriptions",
          organizations_url: "https://api.github.com/users/gugarosa/orgs",
          repos_url: "https://api.github.com/users/gugarosa/repos",
          events_url: "https://api.github.com/users/gugarosa/events{/privacy}",
          received_events_url:
            "https://api.github.com/users/gugarosa/received_events",
          type: "User",
          site_admin: false,
        },
      ],
    };
  },
  computed: {
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