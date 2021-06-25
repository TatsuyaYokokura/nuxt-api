<template>
  <v-col cols="4">
    <v-card>
      <v-list-item three-line>
        <v-list-item-content>
          <div class="text-overline mb-4">OVERLINE</div>
          <v-list-item-title class="text-h5 mb-1">
            {{ post.title }}
          </v-list-item-title>
          <v-list-item-subtitle>
            {{ post.body }}
          </v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
      </v-list-item>

      <v-card-actions>
        <v-btn icon :color="isFavorite" @click="switchFavorite">
          <v-icon>mdi-heart</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  data: () => ({
    favorite: false,
  }),

  computed: {
    isFavorite() {
      if (this.favorite) {
        return 'pink'
      } else {
        return ''
      }
    },
  },

  methods: {
    switchFavorite() {
      this.favorite = !this.favorite
      if (this.favorite) {
        this.$emit('addFavorite', this.post)
      } else {
        this.$emit('removeFavorite', this.post)
      }
    },
  },
}
</script>
