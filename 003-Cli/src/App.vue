<template>
  <div id="app">
    <h1>Annuaire Utilisateurs</h1>
    <p>Mon favori est : {{favorite}}</p>
    <button @click="getUsers"> Recuperer les utilisateurs</button>
    <template v-if="loading">
      <p>Chargement en cours...</p>
    </template>
    <div id="users-list">
      <user
        v-for="user in users"
        :key="user.id"
        :user="user"
        v-on:favoriteUser="defineFavorite"
      />
    </div>
  </div>
</template>

<script>
import user from "./components/user";
export default {
  name: "UserList",
  components: { user },
  data() {
    return {
      users: [],
      loading: false,
      favorite: "Non Définis"
    };
  },
  methods: {
    async getUsers() {
      this.loading = true;
      const res = await fetch("https://jsonplaceholder.typicode.com/users");
      const users = await res.json();
      this.users = users;
      this.loading = false;
    },
    defineFavorite(name) {
      this.favorite = name;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 978px;
  margin: auto;
}
#users-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
