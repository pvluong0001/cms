<template>
  <v-menu offset-y>
    <template v-slot:activator="{ on, attrs }">
      <v-avatar v-bind="attrs" v-on="on" size="36px">
        <img src="icon.png" alt=""/>
      </v-avatar>
    </template>
    <v-list min-width="200px" dense>
      <v-subheader>Settings</v-subheader>
      <v-list-item-group color="primary">
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>List 1</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>List 2</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>

      <v-divider></v-divider>
      <v-subheader>Actions</v-subheader>

      <v-list-item @click="logoutHandle">
        <v-list-item-content>
          <v-list-item-title>Logout</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-menu>
</template>

<script>
  export default {
    name: 'UserAction',
    methods: {
      async logoutHandle() {
        await this.$auth.logout();
      },
    },
  };
</script>

<style scoped>

</style>
