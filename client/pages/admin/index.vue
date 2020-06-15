<template>
  <div>
    <h1>Dashboard</h1>
    <button @click="handleLogout">Logout</button>
  </div>
</template>

<script>
  export default {
    name: 'admin-dashboard',
    layout: 'admin',
    methods: {
      async handleLogout() {
        await this.$auth.logout();

        this.$router.push('/login')
      }
    }
  };
</script>

<style scoped>

</style>
