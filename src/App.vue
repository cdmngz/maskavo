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
    <v-footer dark padless>
    <v-card
      width="100%"
      flat
      tile
    >
      <v-card-title class="teal d-flex justify-center">
        <strong class="subheading">Si quieres saber lo nuevo:</strong>
      </v-card-title>


      <v-card-title class="teal d-flex justify-center">
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4"
          dark
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-title>

      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} — <strong>Maskavo</strong>
      </v-card-text>
    </v-card>
  </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    icons: [
      'mdi-facebook',
      'mdi-twitter',
      'mdi-linkedin',
      'mdi-instagram',
    ],
  })
};
</script>
