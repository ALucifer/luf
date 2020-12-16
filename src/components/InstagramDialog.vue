<template>
  <v-dialog v-model="dialog">
    <v-card>
      <v-img
        :src="this.media.src.large2x"
        max-height="650"
        max-width="940"
      ></v-img>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    dialog: {
      type: Boolean,
      required: true,
      default: false,
    },
    media: {
      type: Object,
      required: false,
    },
  },
};
</script>
