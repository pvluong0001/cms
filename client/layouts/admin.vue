<template>
  <v-app id="inspire">
    <navigation/>

    <v-app-bar
      app
      clipped-left
      dense
    >
      <v-app-bar-nav-icon @click.stop="handleToggleDrawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">Lit {{test ? 'true' : 'false'}}</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <div
        class="text-end"
      >
        <user-action/>
      </div>
    </v-app-bar>

    <v-content>
      <v-container>
        <nuxt/>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import UserAction from '~/components/layouts/UserAction';
  import Navigation from '~/components/layouts/Navigation';
  export default {
    components: {Navigation, UserAction},
    middleware: ['auth'],
    name: 'layout-admin',
    methods: {
      handleToggleDrawer() {
        this.$store.commit('toggleDrawer')
      }
    },
    computed: {
      test() {
        return this.$store.state.drawer
      }
    }
  };
</script>

<style scoped>

</style>
