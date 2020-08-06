<template>
  <v-app>
    <v-app-bar
      app
      color="green lighten-5"
      absolute
      flat
    >
      <div class="d-flex align-center mx-4">
        <v-img
          class="mr-2"
          contain
          src="https://image.flaticon.com/icons/svg/3127/3127151.svg"
          transition="scale-transition"
          width="40"
        />
        <span style="">Maskavo</span>
      </div>

      <v-tabs color="green lighten-1">
        <v-tab to="/"><v-icon>mdi-earth</v-icon></v-tab>
      </v-tabs>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
  })
};
</script>

<style>
  * {
font-family: 'Lora', serif;  }
</style>