<template>
  <div id="fetchApi">
    <h1>github users</h1>
    <input v-model="username" v-on:keyup.13="searchGithubUser" placeholder="search github username" />
    <img :src="user.avatar_url" />
    <h3>{{user.name}}</h3>
  </div>
</template>
<script>
export default {
  name: "FetchApi",
  data() {
    return {
      user: [],
      username: "JuiJenChang",
    };
  },
  methods: {
    searchGithubUser() {
      fetch(`https://api.github.com/users/${this.username}`)
        .then(res => res.json())
        .then(data => (this.user = data))
        .catch((err) => console.log(err));
    },
  },
  created() {
    this.searchGithubUser();
  }
};
</script>

<style>
#fetchApi {
  display: flex;
  flex-direction: column;
  align-items: center;
}
img {
  width: 200px;
  height: 200px;
  margin-top: 10px;
}
</style>
