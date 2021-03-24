<template>
  <v-main class="white">
      <v-img
        dark
        max-height="500px"
        :src="logo('background.jpg')"
      >
        <v-layout fill-height align-center>
          <v-container>
            <v-row align="center" justify="center" class="white--text">
              <v-col cols="12">
                <div
                  :class="{
                    'display-2 font-weight-bold ': $vuetify.breakpoint.smAndUp,
                    'title font-weight-bold': $vuetify.breakpoint.smAndDown,
                  }"
                >
                  Welcome to my page.
                </div>
                <div
                  :class="{
                    headline: $vuetify.breakpoint.smAndUp,
                    'subtitle-1': $vuetify.breakpoint.smAndDown,
                  }"
                >
                  I'm Full-stack developer.
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-layout>
      </v-img>
    </v-main>
</template>

<script>
export default {
  methods: {
    logo(name) {
      return require("../assets/" + name);
    },
  },
}
</script>