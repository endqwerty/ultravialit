<template>
  <div class="hero">
    <v-responsive width="100%">
      <v-img alt="hero splash image" height="100%" contain :src="require('../assets/hero.jpg')">
        <v-container fill-height>
          <v-row align="center" justify="center">
            <h1 :style="'font-size:'+textSize">Ultra Via Lit</h1>
          </v-row>
        </v-container>
      </v-img>
    </v-responsive>
  </div>
</template>

<script>
export default {
  name: "Hero",
  props: {
    msg: String
  },
  computed: {
    textSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "4em";
        case "sm":
          return "4em";
        case "md":
          return "6em";
        case "lg":
          return "6em";
        case "xl":
          return "6em";
      }
      return "1em";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: blueviolet;
}
</style>
