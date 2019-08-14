<template>
  <v-app>
    <v-content>
      <Hero />
    </v-content>
  </v-app>
</template>

<script>
import Hero from "./components/Hero";

export default {
  name: "App",
  components: {
    Hero
  },
  data: () => ({
    //
  })
};
</script>
