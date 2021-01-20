<template>
  <nav>
    <v-app-bar flat app class="indigo lighten-4">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        class="grey--text"
      ></v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Project</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn text class="ma-2 grey--text">
        Sign out
        <v-icon right> mdi-exit-to-app </v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" class=" blue lighten-5">

      <v-list>
        <v-list-item v-for="item in items" :key="item.title" link :to=" item.route ">
          <v-list-item-icon>
            <v-icon class="grey--text text--darken-3">{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="grey--text text--darken-3" >{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        { title: "Dashboard", icon: "mdi-view-dashboard",route:'/'},
        { title: "My Project", icon: "mdi-folder",route:'/project' },
        { title: "Team", icon: "mdi-account",route:'/team' },
      ],
    };
  },
};
</script>