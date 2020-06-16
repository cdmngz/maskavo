<template>
  <v-app>
    <v-app-bar
      app
      color="red lighten-5"
      absolute
      flat
    >
      <div class="d-flex align-center">
        <v-img
          class="shrink mr-2"
          contain
          src="./assets/logo.svg"
          transition="scale-transition"
          width="40"
        />
        <span>MASKAVO</span>
      </div>

      <v-tabs color="green lighten-2">
        <v-tab to="/"><v-icon>mdi-home</v-icon></v-tab>
        <v-tab to="/productos"><v-icon>mdi-shower-head</v-icon></v-tab>
      </v-tabs>
    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>

  </v-app>
</template>

<script>

export default {
  name: 'App',
};
</script>
