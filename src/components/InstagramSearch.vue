<template>
  <v-row>
    <InstagramInput @submit="submit" />
    <v-col v-if="medias && medias.length" cols="12">
      <img
        v-for="(item, key) in medias"
        :key="key"
        :src="item.src.portrait"
        alt=""
        width="200"
        height="200"
      />
    </v-col>
  </v-row>
</template>

<script>
import axios from "axios";
import InstagramInput from "./InstagramInput.vue";

export default {
  components: {
    InstagramInput,
  },
  data() {
    return {
      medias: [],
      word: "",
    };
  },
  created: function() {
    /*axios
      .get("https://api.pexels.com/v1/search?query=nature&per_page=5", {
        headers: {
          Authorization:
            "563492ad6f917000010000016760c2e0166844f7890386c1fd944362",
        },
      })
      .then((res) => {
        this.medias = res.data.photos;
      });*/
  },
  methods: {
    submit(value) {
      axios
        .get(`https://api.pexels.com/v1/search?query=${value}&per_page=5`, {
          headers: {
            Authorization:
              "563492ad6f917000010000016760c2e0166844f7890386c1fd944362",
          },
        })
        .then((res) => {
          this.medias = res.data.photos;
        });
    },
  },
};
</script>
