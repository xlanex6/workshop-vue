<template>
  <div class="container">
    <h1>Login</h1>
    <div class="form-input">
      <label for="email">Email</label>
      <input type="text">
    </div>
    <div class="form-input">
      <label for="password">Password</label>
      <input type="password">
    </div>
    <div class="form-input">
      <button>Sign up</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
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
