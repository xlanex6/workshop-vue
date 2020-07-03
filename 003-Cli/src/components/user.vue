<template>
  <div class="user">
    <h3>{{user.name}}</h3>
    <img
      :src="`https://i.pravatar.cc/150?u=${user.id}`"
      alt="picture"
    >
    <p>{{user.email}}</p>
    <p>{{user.company.name}}</p>
    <a
      :href="user.website"
      target="_banck"
    >website</a>
    <svg
      @click="defineFavorite(user.name)"
      fill="none"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke-width="2"
      viewBox="0 0 24 24"
      stroke="currentColor"
    >
      <path d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"></path>
    </svg>

  </div>
</template>

<script>
export default {
  name: "user",
  props: ["user"],
  methods: {
    defineFavorite(name) {
      this.$emit("favoriteUser", name);
    }
  }
};
</script>

<style lang="css" scoped>
.user {
  flex: 0 0 220px;
  background-color: #ededed;
  margin: 5px;
  justify-content: space-between;
  border-radius: 20px;
}
svg {
  height: 30px;
  width: auto;
}
</style>
