<template>
  <v-card flat color="transparent" max-width="350px">
    <v-card-title>
      <v-layout>
        <v-flex>
          <v-card
            elevation="5"
            class="rounded-xl pa-2 d-flex  justify-center align-center"
            width="100px"
            height="100px"
          >
            <v-img :src="logo(data.logo)" class="w-100" />
          </v-card>
        </v-flex>
        <v-flex xs7 align-self-center>
          <div>{{ data.name }}</div>
          <div v-if="data.description">
            <v-chip small pill dark>{{ data.description }}</v-chip>
          </div>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default: function() {
        return {};
      },
    },
  },
  methods: {
    logo(name) {
      return require("../assets/" + name);
    },
  },
};
</script>
