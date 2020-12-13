<template>
  <v-app>
    <v-main>
      <v-container>
        <InstagramSearch />
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import InstagramSearch from "./components/InstagramSearch.vue";

export default Vue.extend({
  name: "App",

  components: {
    InstagramSearch,
  },

  data: () => ({
    //
  }),
});
</script>
