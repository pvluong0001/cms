<template>
  <v-navigation-drawer
    app
    clipped
    :value="drawer"
  >
    <v-list dense>
      <v-list-item
        v-for="item in items"
        :key="item.text"
        link
      >
        <v-list-item-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>
            {{ item.text }}
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-subheader class="mt-4 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
      <v-list-item
        class="mt-4"
        link
      >
        <v-list-item-action>
          <v-icon color="grey darken-1">mdi-plus-circle-outline</v-icon>
        </v-list-item-action>
        <v-list-item-title class="grey--text text--darken-1">Browse Channels</v-list-item-title>
      </v-list-item>
      <v-list-item link>
        <v-list-item-action>
          <v-icon color="grey darken-1">mdi-cog</v-icon>
        </v-list-item-action>
        <v-list-item-title class="grey--text text--darken-1">Manage Subscriptions</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
  import { mapState } from 'vuex';

  export default {
    name: 'Navigation',
    data: () => ({
      items: [
        {icon: 'mdi-trending-up', text: 'Most Popular'},
        {icon: 'mdi-youtube-subscription', text: 'Subscriptions'},
        {icon: 'mdi-history', text: 'History'},
        {icon: 'mdi-playlist-play', text: 'Playlists'},
        {icon: 'mdi-clock', text: 'Watch Later'},
      ],
    }),
    computed: {
      ...mapState(['drawer'])
    }
  };
</script>

<style scoped>

</style>
