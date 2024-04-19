<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-btn color="primary" @click="homeNav"> Get prediction </v-btn>
      </div>

      <v-spacer></v-spacer>
      <div class="d-flex align-center">
        <h1 color="primary">movie AI</h1>
      </div>
      <v-spacer></v-spacer>

      <v-btn color="primary" @click="historyNav">predictions history </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import router from "./router/index";
export default {
  name: "App",
  data: () => ({
    //
  }),
  methods: {
    homeNav() {
      if (router.currentRoute.path == "/") return;

      router.push("/");
    },
    historyNav() {
      if (router.currentRoute.path == "/history") return;
      // console.log(router.currentRoute.path);
      router.push("/history");
    },
  },
};
</script>
