<template>
  <div class="hero">
    <v-responsive width="100%">
      <v-row no-gutters v-if="this.$vuetify.breakpoint.name == 'xs'">
        <v-col>
          <v-img
            alt="hero splash image"
            height="100%"
            contain
            :src="require('../assets/hero.jpg')"
            position="top"
          ></v-img>
        </v-col>
      </v-row>
      <With-Root :showIf="checkSizeGreaterThanSM">
        <v-img
          alt="hero splash image"
          height="100%"
          contain
          :src="require('../assets/hero.jpg')"
          position="top"
        >
          <v-row no-gutters>
            <v-col>
              <h1 :style="textSize">Ultra Via Lit</h1>
            </v-col>
            <v-col align="right">
              <iframe
                src="https://open.spotify.com/embed/artist/4BnxnyUhIr7TVm5p6tBWU6"
                width="375"
                height="400"
                frameborder="0"
                allowtransparency="true"
                allow="encrypted-media"
              ></iframe>
            </v-col>
          </v-row>
        </v-img>
      </With-Root>
    </v-responsive>
  </div>
</template>

<script>
import WithRoot from "./WithRoot.vue.js";
export default {
  name: "Hero",
  props: {
    msg: String
  },
  components: {
    WithRoot
  },
  computed: {
    textSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "font-size: 4em; text-align: center";
        case "sm":
          return "font-size: 4em; text-align: center";
        case "md":
          return "font-size: 6em";
        case "lg":
          return "font-size: 6em";
        case "xl":
          return "font-size: 6em";
      }
      return "1em";
    },
    checkSizeGreaterThanSM() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return false;
        case "sm":
          return true;
        case "md":
          return true;
        case "lg":
          return true;
        case "xl":
          return true;
      }
      return "1em";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hero {
  background-color: black;
}
h1 {
  color: whitesmoke;
}
</style>
