<template>
  <div id="dashboard">
    <h1>That's the dashboard!</h1>
    <p>You should only get here if you're authenticated!</p>
    <p v-if="user">Your email address: {{ user.email }}</p>
  </div>
</template>

<script>
  export default {
    computed: {
      user() {
        var user = this.$store.getters.user ? this.$store.getters.user : false;
        console.log(user);
        return user
      },
    },
    created () {
      this.$store.dispatch('fetchUser')
    },
  }
</script>

<style scoped>
  h1, p {
    text-align: center;
  }

  p {
    color: red;
  }
</style>