<template>
  <section>
    <div v-for="user in users" :key="user.id">
      <h3>{{ user.name }}</h3>
      <h4>{{ user.email }}</h4>
      <br>
    </div>
  </section>
</template>

<script>
export default {
  name: "Contacts",
  data() {
    return {
      users: [],
    };
  },
  async asyncData({ $axios }) {
    const users = await $axios.$get(
      "https://jsonplaceholder.typicode.com/users"
    );
    return { users };
  },
};
</script>

<style scoped>
.navbar-brand img {
  width: 5em;
}
</style>