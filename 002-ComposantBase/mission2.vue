<template>
  <div class="container">
    <h1>Login</h1>
    <div class="form-input">
      <label for="email">Email</label>
      <input
        type="text"
        v-model="email"
      >
    </div>
    <div class="form-input">
      <label for="password">Password</label>
      <input
        type="password"
        v-model="password"
      >
    </div>
    <div class="form-input">
      <button
        @click="login"
        :disabled="email && password == ''"
      >Connexion</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    login() {
      alert(
        `vous etes connecté en tant que ${this.email} avec le mot de passe : ${this.password}`
      );
    }
  }
};
</script>

<style scoped>
.container {
  width: 978px;
  margin: auto;
  text-align: center;
}

.form-input {
  margin-bottom: 20px;
}
.form-input label {
  margin-right: 10px;
}
</style>
