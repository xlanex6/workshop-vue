<template>
  <div class="container">
    <h1>Login</h1>
    <div class="form-input">
      <label for="name">Name</label>
      <input
        type="text"
        v-model="name"
      >
      <span v-if="name !== ''">
        {{name.length}}
      </span>
    </div>
    <div class="form-input">
      <label for="name">Age</label>
      <input
        type="number"
        v-model.number="age"
      >
      <span v-if="age > 18">vous etes majeur</span>
      <span v-else>vous etes mineur</span>
    </div>
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
        :disabled="!isValid"
      >Connexion</button>
      <button @click="reset">reset</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      email: "",
      name: "",
      password: "",
      age: 0,
      isValid: false
    };
  },
  methods: {
    login() {
      alert(
        `vous ets connecté en tant que ${this.email} avec le mot de passe : ${this.password}`
      );
    },
    validation() {
      if (this.email !== "" && this.name !== "" && this.password !== "") {
        this.isValid = true;
      } else {
        this.isValid = false;
      }
    },
    reset() {
      (this.email = ""), (this.age = 0), (this.name = ""), (this.password = "");
    }
  },
  watch: {
    email: "validation",
    password() {
      this.validation();
    },
    name() {
      this.validation();
    },
    age(v) {
      if (v < 0) {
        this.age = 0;
      }
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
