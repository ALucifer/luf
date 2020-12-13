<template>
  <v-row>
    <InstagramInput @submit="submit" />
    <v-col v-if="medias && medias.length" cols="12">
      <v-row>
        <v-col 
          cols="3"
          v-for="(item, key) in medias"
          :key="key"
        >
          <img
            :src="item.src.portrait"
            alt=""
            width="200"
            height="200"
            @click="showImage(item)"
          />
        </v-col>
      </v-row>
    </v-col>
    <InstagramDialog />
  </v-row>
</template>

<script>
import axios from "axios";
import InstagramInput from "./InstagramInput.vue";
import InstagramDialog from "./InstagramDialog.vue"

export default {
  components: {
    InstagramInput, InstagramDialog
  },
  data() {
    return {
      medias: [],
      selectedMedia: null,
      word: "",
    };
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
    showImage(media) {
      this.selectedMedia = media;
    }
  },
};
</script>
