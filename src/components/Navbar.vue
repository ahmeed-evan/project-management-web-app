<template>
  <nav>
    <v-app-bar flat app class="grey lighten-4">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        class="grey--text"
      ></v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Project</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn depressed class="ma-2 grey--text">
        Sign out
        <v-icon right> mdi-exit-to-app </v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" class="grey">
      <v-list>

      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      drawer: false,
    };
  },
};
</script>