<template>
  <v-col cols="12">{{ favorite.id }}: {{ favorite.title }} </v-col>
</template>

<script>
export default {
  props: {
    favorite: {
      type: Object,
      required: true,
    },
  },
}
</script>
