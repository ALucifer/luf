<template>
  <v-col cols="12">
    <v-row>
      <v-col cols="10">
        <v-text-field
          label="Recherche des images"
          v-model="word"
        ></v-text-field>
      </v-col>
      <v-col cols="2">
        <v-btn color="primary" @click="submit">Rechercher</v-btn>
      </v-col>
    </v-row>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
      word: "",
    };
  },
  methods: {
    submit(event) {
      this.$emit("submit", this.word);
    },
  },
};
</script>
