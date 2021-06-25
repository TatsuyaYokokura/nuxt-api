<template>
  <div>
    <Header />
    <v-container>
      <v-row>
        <PostsList
          v-for="post in posts"
          :key="post.id"
          :post="post"
          @addFavorite="addFavorite"
          @removeFavorite="removeFavorite"
        />
      </v-row>
    </v-container>
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get(
      'https://jsonplaceholder.typicode.com/posts'
    )
    return { posts }
  },

  data: () => ({
    favorites: [],
  }),

  methods: {
    addFavorite(post) {
      this.favorites.push(post)
    },
    removeFavorite(post) {
      const index = this.favorites.find((favorite) => favorite.id === post.id)
      this.favorites.splice(index, 1)
    },
  },
}
</script>
