<template>
  <div class="hero">
    <v-responsive width="100%">
      <v-row no-gutters v-if="!$vuetify.breakpoint.mdAndUp">
        <v-col>
          <v-img
            alt="hero splash image"
            contain
            :src="require('../assets/hero.jpg')"
            position="top"
          ></v-img>
        </v-col>
      </v-row>
      <With-Root :showIf="$vuetify.breakpoint.mdAndUp">
        <v-img
          alt="hero splash image"
          height="100%"
          contain
          :src="require('../assets/hero.jpg')"
          position="top"
        >
          <v-row no-gutters>
            <v-col cols="12" md="auto">
              <h1
                :class="currentBreakpoint"
                v-bind:style="dynamicTopLeftPadding"
              >
                Ultra Via Lit
              </h1>
            </v-col>
            <v-spacer></v-spacer>
            <v-col cols="12" md="auto" align-self="end">
              <iframe
                src="https://open.spotify.com/embed/artist/4BnxnyUhIr7TVm5p6tBWU6"
                id="spotify-frame"
                :class="currentBreakpoint"
                :width="spotifyWidth"
                height="400"
                frameborder="0"
                allowtransparency="true"
                allow="encrypted-media"
                v-bind:style="dynamicTopRightPadding"
              ></iframe>
            </v-col>
          </v-row>
        </v-img>
      </With-Root>
    </v-responsive>
  </div>
</template>

<script>
import WithRoot from './WithRoot.vue.js'
const ratio = 0.03
export default {
  name: 'Hero',
  props: {
    msg: String,
  },
  components: {
    WithRoot,
  },
  computed: {
    currentBreakpoint() {
      return this.$vuetify.breakpoint.name
    },
    dynamicTopLeftPadding() {
      if (this.$vuetify.breakpoint.mdAndUp)
        return `padding-left: ${this.$vuetify.breakpoint.width * ratio}px;
        padding-top: ${this.$vuetify.breakpoint.width * ratio - 36}px;`
      else return ''
    },
    dynamicTopRightPadding() {
      if (this.$vuetify.breakpoint.mdAndUp)
        return `padding-right: ${this.$vuetify.breakpoint.width * ratio}px;
        padding-top: ${this.$vuetify.breakpoint.width * ratio}px;`
      else return ''
    },
    spotifyWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
          return '100%'
        case 'sm':
          return '100%'
        case 'md':
          return '100%'
        case 'lg':
          return '400px'
        case 'xl':
          return '400px'
        default:
          return '100%'
      }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.hero {
  background-color: black;
}
h1 {
  color: whitesmoke;
  &.xs {
    font-size: 3em;
    text-align: center;
  }
  &.sm {
    font-size: 4em;
    text-align: center;
  }
  &.md {
    font-size: 6em;
  }
  &.lg {
    font-size: 6em;
  }
  &.xl {
    font-size: 6em;
  }
}
#spotify-frame {
  // &.xs {
  // }
  // &.sm {
  // }
  // &.md {
  // }
  &.lg {
    padding-top: 10px;
    padding-right: 10px;
  }
  &.xl {
    padding-top: 10px;
    padding-right: 10px;
  }
}
</style>
