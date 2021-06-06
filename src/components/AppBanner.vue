<template>
  <v-main class="white">
    <v-img dark max-height="500px" :src="Banner">
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
                 <v-avatar size="60" class="mb-4">
                    <v-img
                      position="top"
                      :src="user"
                      class="rounded-lg flex"
                    ></v-img>
                  </v-avatar>
                   Welcome to my portfolio.
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
import Banner from "@/assets/banner/photo-1508830524289-0adcbe822b40.jpeg";
import user from "@/assets/165173659_448587036222196_4093650296544086329_n.jpeg";
export default {
  data() {
    return {
      Banner,
      user
    };
  },
};
</script>