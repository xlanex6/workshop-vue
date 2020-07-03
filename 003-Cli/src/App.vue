<template>
  <div id="app">
    <h1>Annuaire Utilisateurs</h1>
    <p>Mon favori est : {{favorite}}</p>
    <button> Recuperer les utilisateurs</button>

    <div id="users-list">
      USERS ....
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {};
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
