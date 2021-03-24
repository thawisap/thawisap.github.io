<template>
  <v-app-bar flat absolute color="transparent" dark height="120px">
    <v-layout justify-center>
      <v-container>
        <v-layout>
          <div
            :class="{
              'display-1 font-weight-bold': $vuetify.breakpoint.smAndUp,
              'title font-weight-bold': $vuetify.breakpoint.smAndDown,
            }"
          >
            Precharat
          </div>
          <v-spacer></v-spacer>
          <v-toolbar-items class="text-right">
            <v-btn v-for="({ text, link }, key) in menus"
              :key="key"
              :x-small="$vuetify.breakpoint.smAndDown"
              @click="$vuetify.goTo(link,options )"
              text
            >{{ text }}</v-btn>
          </v-toolbar-items>
        </v-layout>
      </v-container>
    </v-layout>
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    options: {
      duration: 300,
      offset: 0,
      easing: "easeInOutCubic",
    },
    menus: [
      { text: 'About', link: '#about'},
      { text: 'Skill', link: '#skill'},
      { text: 'Contact', link: '#contact'},
    ]
  }),
};
</script>